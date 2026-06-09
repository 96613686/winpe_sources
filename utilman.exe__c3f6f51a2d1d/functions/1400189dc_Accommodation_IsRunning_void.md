# Accommodation::IsRunning(void)

- ea: `0x1400189dc`
- end: `0x140018a66`
- name: `?IsRunning@Accommodation@@QEAAHXZ`
- size: `138`
- prototype: `__int64 __fastcall(Accommodation *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014844`
- `0x14002227c`
- `0x140022b10`

## callees

- `0x1400187fc`
- `0x1400189dc`
- `0x140018f28`
- `0x140026a44`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140018a47`
- `KERNEL32!CloseHandle` at `0x140018a47`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140018a03`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140018a03`

## pseudocode

```c
__int64 __fastcall Accommodation::IsRunning(Accommodation *this)
{
  unsigned int v2; // edi
  unsigned int v3; // eax
  const unsigned __int16 *v4; // rcx
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  if ( !wcscmp_0(*((const wchar_t **)this + 5), L"SystemSetting") )
  {
    v3 = _o__wtoi(*((_QWORD *)this + 3));
    if ( v3 < 0x16 )
      return (unsigned int)SystemSettings::IsOn(this, v3);
  }
  else
  {
    v4 = (const unsigned __int16 *)*((_QWORD *)this + 7);
    if ( !*((_DWORD *)v4 - 4) )
      return 0;
    hObject = 0;
    if ( (unsigned int)Accommodation::FindProcess(v4, &hObject) )
    {
      CloseHandle(hObject);
      return 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400189dc  mov     [rsp+arg_0], rbx
0x1400189e1  push    rdi
0x1400189e2  sub     rsp, 20h
0x1400189e6  mov     rbx, rcx
0x1400189e9  lea     rdx, aSystemsetting; "SystemSetting"
0x1400189f0  mov     rcx, [rcx+28h]; String1
0x1400189f4  xor     edi, edi
0x1400189f6  call    wcscmp_0
0x1400189fb  test    eax, eax
0x1400189fd  jnz     short loc_140018A22
0x1400189ff  mov     rcx, [rbx+18h]
0x140018a03  call    cs:__imp__o__wtoi
0x140018a0a  nop     dword ptr [rax+rax+00h]
0x140018a0f  cmp     eax, 16h
0x140018a12  jnb     short loc_140018A58
0x140018a14  mov     edx, eax
0x140018a16  mov     rcx, rbx
0x140018a19  call    ?IsOn@SystemSettings@@SAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z; SystemSettings::IsOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint)
0x140018a1e  mov     edi, eax
0x140018a20  jmp     short loc_140018A58
0x140018a22  mov     rcx, [rbx+38h]; unsigned __int16 *
0x140018a26  cmp     [rcx-10h], edi
0x140018a29  jnz     short loc_140018A2F
0x140018a2b  xor     eax, eax
0x140018a2d  jmp     short loc_140018A5A
0x140018a2f  lea     rdx, [rsp+28h+hObject]; void **
0x140018a34  mov     [rsp+28h+hObject], rdi
0x140018a39  call    ?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z; Accommodation::FindProcess(ushort const *,void * *,int)
0x140018a3e  test    eax, eax
0x140018a40  jz      short loc_140018A58
0x140018a42  mov     rcx, [rsp+28h+hObject]; hObject
0x140018a47  call    cs:__imp_CloseHandle
0x140018a4e  nop     dword ptr [rax+rax+00h]
0x140018a53  mov     edi, 1
0x140018a58  mov     eax, edi
0x140018a5a  mov     rbx, [rsp+28h+arg_0]
0x140018a5f  add     rsp, 20h
0x140018a63  pop     rdi
0x140018a64  retn
```
