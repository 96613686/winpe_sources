# CDVRConfigure::GetDirectory(ushort * *)

- ea: `0x1800561a0`
- end: `0x1800562a0`
- name: `?GetDirectory@CDVRConfigure@@UEAAJPEAPEAG@Z`
- size: `256`
- prototype: `__int64 __fastcall(CDVRConfigure *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180001c00`
- `0x1800561a0`
- `0x18005f880`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x180056263`
- `KERNEL32!GetTempPath2W` at `0x18005628d`
- `KERNEL32!GetTempPath2W` at `0x180056263`
- `KERNEL32!GetTempPath2W` at `0x18005628d`
- `ole32!CoTaskMemAlloc` at `0x180056205`
- `ole32!CoTaskMemAlloc` at `0x180056278`
- `ole32!CoTaskMemAlloc` at `0x180056205`
- `ole32!CoTaskMemAlloc` at `0x180056278`
- `ole32!CoTaskMemFree` at `0x180056235`
- `ole32!CoTaskMemFree` at `0x180056235`

## pseudocode

```c
__int64 __fastcall CDVRConfigure::GetDirectory(CDVRConfigure *this, LPVOID *a2, const unsigned __int16 *a3)
{
  SBECoreUtil *v6; // rcx
  unsigned __int16 *v7; // rax
  HKEY v8; // rdx
  const unsigned __int16 *v9; // r8
  int RegStringValW; // eax
  int TempPath2W; // eax
  unsigned __int16 *v12; // rax
  unsigned __int8 *v13; // [rsp+28h] [rbp-20h]
  unsigned __int8 *v14; // [rsp+28h] [rbp-20h]
  SIZE_T cb; // [rsp+30h] [rbp-18h] BYREF

  LODWORD(cb) = 0;
  if ( !a2 )
    return 2147500035LL;
  v6 = (SBECoreUtil *)*((_QWORD *)this + 2);
  if ( !v6 )
    return 2147549183LL;
  if ( SBECoreUtil::GetRegStringValW(v6, (HKEY)a2, a3, (const unsigned __int16 *)&cb, 0, v13) && (unsigned int)cb > 2 )
  {
    v7 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
    *a2 = v7;
    if ( v7 )
    {
      RegStringValW = SBECoreUtil::GetRegStringValW(
                        *((SBECoreUtil **)this + 2),
                        v8,
                        v9,
                        (const unsigned __int16 *)&cb,
                        (unsigned int *)v7,
                        v14);
LABEL_9:
      if ( RegStringValW )
        return 0;
      CoTaskMemFree(*a2);
      *a2 = 0;
      return 2147500037LL;
    }
  }
  else
  {
    TempPath2W = GetTempPath2W(0, 0);
    if ( !TempPath2W )
      return 2147500037LL;
    LODWORD(cb) = TempPath2W + 1;
    v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(TempPath2W + 1));
    *a2 = v12;
    if ( v12 )
    {
      RegStringValW = GetTempPath2W((unsigned int)cb, v12);
      LODWORD(cb) = RegStringValW;
      goto LABEL_9;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800561a0  mov     [rsp+arg_10], rbx
0x1800561a5  push    rdi
0x1800561a6  sub     rsp, 40h
0x1800561aa  mov     rax, cs:__security_cookie
0x1800561b1  xor     rax, rsp
0x1800561b4  mov     [rsp+48h+var_10], rax
0x1800561b9  mov     dword ptr [rsp+48h+cb], 0
0x1800561c1  mov     rbx, rdx
0x1800561c4  mov     rdi, rcx
0x1800561c7  test    rdx, rdx
0x1800561ca  jnz     short loc_1800561D3
0x1800561cc  mov     eax, 80004003h
0x1800561d1  jmp     short loc_180056247
0x1800561d3  mov     rcx, [rcx+10h]; this
0x1800561d7  test    rcx, rcx
0x1800561da  jnz     short loc_1800561E3
0x1800561dc  mov     eax, 8000FFFFh
0x1800561e1  jmp     short loc_180056247
0x1800561e3  lea     r9, [rsp+48h+cb]; unsigned __int16 *
0x1800561e8  mov     [rsp+48h+var_28], 0; unsigned int *
0x1800561f1  call    ?GetRegStringValW@SBECoreUtil@@YAHPEAUHKEY__@@PEBG1PEAKPEAE@Z; SBECoreUtil::GetRegStringValW(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *)
0x1800561f6  test    eax, eax
0x1800561f8  jz      short loc_18005625F
0x1800561fa  cmp     dword ptr [rsp+48h+cb], 2
0x1800561ff  jbe     short loc_18005625F
0x180056201  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180056205  call    cs:__imp_CoTaskMemAlloc
0x18005620b  mov     [rbx], rax
0x18005620e  test    rax, rax
0x180056211  jz      loc_180056299
0x180056217  mov     rcx, [rdi+10h]; this
0x18005621b  lea     r9, [rsp+48h+cb]; unsigned __int16 *
0x180056220  mov     [rsp+48h+var_28], rax; unsigned int *
0x180056225  call    ?GetRegStringValW@SBECoreUtil@@YAHPEAUHKEY__@@PEBG1PEAKPEAE@Z; SBECoreUtil::GetRegStringValW(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *)
0x18005622a  test    eax, eax
0x18005622c  jz      short loc_180056232
0x18005622e  xor     eax, eax
0x180056230  jmp     short loc_180056247
0x180056232  mov     rcx, [rbx]; pv
0x180056235  call    cs:__imp_CoTaskMemFree
0x18005623b  mov     qword ptr [rbx], 0
0x180056242  mov     eax, 80004005h
0x180056247  mov     rcx, [rsp+48h+var_10]
0x18005624c  xor     rcx, rsp; StackCookie
0x18005624f  call    __security_check_cookie
0x180056254  mov     rbx, [rsp+48h+arg_10]
0x180056259  add     rsp, 40h
0x18005625d  pop     rdi
0x18005625e  retn
0x18005625f  xor     edx, edx
0x180056261  xor     ecx, ecx
0x180056263  call    cs:__imp_GetTempPath2W
0x180056269  test    eax, eax
0x18005626b  jz      short loc_180056242
0x18005626d  inc     eax
0x18005626f  mov     ecx, eax
0x180056271  add     rcx, rcx; cb
0x180056274  mov     dword ptr [rsp+48h+cb], eax
0x180056278  call    cs:__imp_CoTaskMemAlloc
0x18005627e  mov     [rbx], rax
0x180056281  test    rax, rax
0x180056284  jz      short loc_180056299
0x180056286  mov     ecx, dword ptr [rsp+48h+cb]
0x18005628a  mov     rdx, rax
0x18005628d  call    cs:__imp_GetTempPath2W
0x180056293  mov     dword ptr [rsp+48h+cb], eax
0x180056297  jmp     short loc_18005622A
0x180056299  mov     eax, 8007000Eh
0x18005629e  jmp     short loc_180056247
```
