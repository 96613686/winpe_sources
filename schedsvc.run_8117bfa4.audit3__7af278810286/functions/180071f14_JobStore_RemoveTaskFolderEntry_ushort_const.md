# JobStore::RemoveTaskFolderEntry(ushort const *)

- ea: `0x180071f14`
- end: `0x180072077`
- name: `?RemoveTaskFolderEntry@JobStore@@AEBAJPEBG@Z`
- size: `355`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d7ac`

## callees

- `0x18002123c`
- `0x18002db40`
- `0x180033700`
- `0x180047210`
- `0x180059140`
- `0x180071f14`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180071f3e`
- `msvcrt!wcsrchr` at `0x180071f3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180072058`
- `OLEAUT32!__imp_SysFreeString` at `0x180072058`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180071fd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180071fd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobStore::RemoveTaskFolderEntry(JobStore *this, const unsigned __int16 *a2)
{
  int v2; // ebp
  wchar_t *v4; // rax
  const WCHAR *v5; // rsi
  int v6; // eax
  int v7; // edx
  unsigned int v8; // edi
  LSTATUS v9; // eax
  int v10; // edx
  char v11; // r8
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp+20h] BYREF

  v2 = (int)a2;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&Str, a2);
  v4 = wcsrchr(Str, 0x5Cu);
  v5 = v4;
  if ( v4 )
  {
    *v4 = 0;
    v5 = v4 + 1;
  }
  hKey = 0;
  v6 = JobStore::RegTreeEntryOpen(this, Str, &hKey);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v9 = RegDeleteKeyExW(hKey, v5, 0x20006u, 0);
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      else
        v8 = v9;
      if ( !tsched::IsErrorNotFound((tsched *)v8, v10)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          v2,
          v11);
      }
    }
    else
    {
      v8 = 0;
    }
  }
  else if ( !tsched::IsErrorNotFound((tsched *)(unsigned int)v6, v7)
         && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      v2,
      v8);
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  SysFreeString(Str);
  return v8;
}

```

## disassembly

```asm
0x180071f14  mov     [rsp+arg_0], rbp
0x180071f19  mov     [rsp+arg_8], rsi
0x180071f1e  push    rdi
0x180071f1f  sub     rsp, 30h
0x180071f23  mov     rbp, rdx
0x180071f26  mov     rdi, rcx
0x180071f29  lea     rcx, [rsp+38h+Str]; this
0x180071f2e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180071f33  nop
0x180071f34  mov     edx, 5Ch ; '\'; Ch
0x180071f39  mov     rcx, [rsp+38h+Str]; Str
0x180071f3e  call    cs:__imp_wcsrchr
0x180071f45  nop     dword ptr [rax+rax+00h]
0x180071f4a  mov     rsi, rax
0x180071f4d  test    rax, rax
0x180071f50  jz      short loc_180071F5B
0x180071f52  xor     ecx, ecx
0x180071f54  mov     [rax], cx
0x180071f57  add     rsi, 2
0x180071f5b  mov     [rsp+38h+hKey], 0
0x180071f64  lea     r8, [rsp+38h+hKey]; HKEY *
0x180071f69  mov     rdx, [rsp+38h+Str]; unsigned __int16 *
0x180071f6e  mov     rcx, rdi; this
0x180071f71  call    ?RegTreeEntryOpen@JobStore@@AEBAJPEBGPEAPEAUHKEY__@@K@Z; JobStore::RegTreeEntryOpen(ushort const *,HKEY__ * *,ulong)
0x180071f76  mov     edi, eax
0x180071f78  test    eax, eax
0x180071f7a  jns     short loc_180071FC4
0x180071f7c  mov     ecx, eax; this
0x180071f7e  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180071f83  test    al, al
0x180071f85  jnz     loc_180072048
0x180071f8b  lea     rax, WPP_GLOBAL_Control
0x180071f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180071f99  cmp     rcx, rax
0x180071f9c  jz      loc_180072048
0x180071fa2  test    dword ptr [rcx+1Ch], 40000h
0x180071fa9  jz      loc_180072048
0x180071faf  cmp     byte ptr [rcx+19h], 2
0x180071fb3  jb      loc_180072048
0x180071fb9  mov     edx, 20h ; ' '
0x180071fbe  mov     [rsp+38h+var_18], edi
0x180071fc2  jmp     short loc_180072031
0x180071fc4  xor     r9d, r9d; Reserved
0x180071fc7  mov     r8d, 20006h; samDesired
0x180071fcd  mov     rdx, rsi; lpSubKey
0x180071fd0  mov     rcx, [rsp+38h+hKey]; hKey
0x180071fd5  call    cs:__imp_RegDeleteKeyExW
0x180071fdc  nop     dword ptr [rax+rax+00h]
0x180071fe1  mov     r8d, eax
0x180071fe4  test    eax, eax
0x180071fe6  jz      short loc_180072046
0x180071fe8  test    eax, eax
0x180071fea  jg      short loc_180071FF0
0x180071fec  mov     edi, eax
0x180071fee  jmp     short loc_180071FFA
0x180071ff0  movzx   edi, r8w
0x180071ff4  or      edi, 80070000h
0x180071ffa  mov     ecx, edi; this
0x180071ffc  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180072001  test    al, al
0x180072003  jnz     short loc_180072048
0x180072005  lea     rax, WPP_GLOBAL_Control
0x18007200c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072013  cmp     rcx, rax
0x180072016  jz      short loc_180072048
0x180072018  test    dword ptr [rcx+1Ch], 40000h
0x18007201f  jz      short loc_180072048
0x180072021  cmp     byte ptr [rcx+19h], 2
0x180072025  jb      short loc_180072048
0x180072027  mov     edx, 21h ; '!'
0x18007202c  mov     [rsp+38h+var_18], r8d
0x180072031  mov     r9, rbp
0x180072034  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18007203b  mov     rcx, [rcx+10h]
0x18007203f  call    WPP_SF_Sd
0x180072044  jmp     short loc_180072048
0x180072046  xor     edi, edi
0x180072048  lea     rcx, [rsp+38h+hKey]; this
0x18007204d  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180072052  nop
0x180072053  mov     rcx, [rsp+38h+Str]; bstrString
0x180072058  call    cs:__imp_SysFreeString
0x18007205f  nop     dword ptr [rax+rax+00h]
0x180072064  mov     eax, edi
0x180072066  mov     rbp, [rsp+38h+arg_0]
0x18007206b  mov     rsi, [rsp+38h+arg_8]
0x180072070  add     rsp, 30h
0x180072074  pop     rdi
0x180072075  retn
```
