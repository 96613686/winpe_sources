# JobStore::RemoveTaskFolderEntry(ushort const *)

- ea: `0x18006e7d4`
- end: `0x18006e924`
- name: `?RemoveTaskFolderEntry@JobStore@@AEBAJPEBG@Z`
- size: `336`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800213f8`

## callees

- `0x180017410`
- `0x180021300`
- `0x18002643c`
- `0x180045410`
- `0x180056794`
- `0x18006e7d4`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18006e7fe`
- `msvcrt!wcsrchr` at `0x18006e7fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18006e90c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006e90c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006e88f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006e88f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobStore::RemoveTaskFolderEntry(JobStore *this, const unsigned __int16 *a2)
{
  int v2; // ebp
  wchar_t *v4; // rax
  unsigned int v5; // r9d
  const WCHAR *v6; // rsi
  int v7; // eax
  int v8; // edx
  unsigned int v9; // edi
  LSTATUS v10; // eax
  int v11; // edx
  char v12; // r8
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp+20h] BYREF

  v2 = (int)a2;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&Str, a2);
  v4 = wcsrchr(Str, 0x5Cu);
  v6 = v4;
  if ( v4 )
  {
    *v4 = 0;
    v6 = v4 + 1;
  }
  hKey = 0;
  v7 = JobStore::RegTreeEntryOpen(this, Str, &hKey, v5);
  v9 = v7;
  if ( v7 >= 0 )
  {
    v10 = RegDeleteKeyExW(hKey, v6, 0x20006u, 0);
    if ( v10 )
    {
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      else
        v9 = v10;
      if ( !tsched::IsErrorNotFound((tsched *)v9, v11)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          v2,
          v12);
      }
    }
    else
    {
      v9 = 0;
    }
  }
  else if ( !tsched::IsErrorNotFound((tsched *)(unsigned int)v7, v8)
         && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      v2,
      v9);
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  SysFreeString(Str);
  return v9;
}

```

## disassembly

```asm
0x18006e7d4  mov     [rsp+arg_0], rbp
0x18006e7d9  mov     [rsp+arg_8], rsi
0x18006e7de  push    rdi
0x18006e7df  sub     rsp, 30h
0x18006e7e3  mov     rbp, rdx
0x18006e7e6  mov     rdi, rcx
0x18006e7e9  lea     rcx, [rsp+38h+Str]; this
0x18006e7ee  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18006e7f3  nop
0x18006e7f4  mov     edx, 5Ch ; '\'; Ch
0x18006e7f9  mov     rcx, [rsp+38h+Str]; Str
0x18006e7fe  call    cs:__imp_wcsrchr
0x18006e804  mov     rsi, rax
0x18006e807  test    rax, rax
0x18006e80a  jz      short loc_18006E815
0x18006e80c  xor     ecx, ecx
0x18006e80e  mov     [rax], cx
0x18006e811  add     rsi, 2
0x18006e815  mov     [rsp+38h+hKey], 0
0x18006e81e  lea     r8, [rsp+38h+hKey]; HKEY *
0x18006e823  mov     rdx, [rsp+38h+Str]; unsigned __int16 *
0x18006e828  mov     rcx, rdi; this
0x18006e82b  call    ?RegTreeEntryOpen@JobStore@@AEBAJPEBGPEAPEAUHKEY__@@K@Z; JobStore::RegTreeEntryOpen(ushort const *,HKEY__ * *,ulong)
0x18006e830  mov     edi, eax
0x18006e832  test    eax, eax
0x18006e834  jns     short loc_18006E87E
0x18006e836  mov     ecx, eax; this
0x18006e838  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18006e83d  test    al, al
0x18006e83f  jnz     loc_18006E8FC
0x18006e845  lea     rax, WPP_GLOBAL_Control
0x18006e84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e853  cmp     rcx, rax
0x18006e856  jz      loc_18006E8FC
0x18006e85c  test    dword ptr [rcx+1Ch], 40000h
0x18006e863  jz      loc_18006E8FC
0x18006e869  cmp     byte ptr [rcx+19h], 2
0x18006e86d  jb      loc_18006E8FC
0x18006e873  mov     edx, 20h ; ' '
0x18006e878  mov     [rsp+38h+var_18], edi
0x18006e87c  jmp     short loc_18006E8E5
0x18006e87e  xor     r9d, r9d; Reserved
0x18006e881  mov     r8d, 20006h; samDesired
0x18006e887  mov     rdx, rsi; lpSubKey
0x18006e88a  mov     rcx, [rsp+38h+hKey]; hKey
0x18006e88f  call    cs:__imp_RegDeleteKeyExW
0x18006e895  mov     r8d, eax
0x18006e898  test    eax, eax
0x18006e89a  jz      short loc_18006E8FA
0x18006e89c  test    eax, eax
0x18006e89e  jg      short loc_18006E8A4
0x18006e8a0  mov     edi, eax
0x18006e8a2  jmp     short loc_18006E8AE
0x18006e8a4  movzx   edi, r8w
0x18006e8a8  or      edi, 80070000h
0x18006e8ae  mov     ecx, edi; this
0x18006e8b0  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18006e8b5  test    al, al
0x18006e8b7  jnz     short loc_18006E8FC
0x18006e8b9  lea     rax, WPP_GLOBAL_Control
0x18006e8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e8c7  cmp     rcx, rax
0x18006e8ca  jz      short loc_18006E8FC
0x18006e8cc  test    dword ptr [rcx+1Ch], 40000h
0x18006e8d3  jz      short loc_18006E8FC
0x18006e8d5  cmp     byte ptr [rcx+19h], 2
0x18006e8d9  jb      short loc_18006E8FC
0x18006e8db  mov     edx, 21h ; '!'
0x18006e8e0  mov     [rsp+38h+var_18], r8d
0x18006e8e5  mov     r9, rbp
0x18006e8e8  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006e8ef  mov     rcx, [rcx+10h]
0x18006e8f3  call    WPP_SF_Sd
0x18006e8f8  jmp     short loc_18006E8FC
0x18006e8fa  xor     edi, edi
0x18006e8fc  lea     rcx, [rsp+38h+hKey]; this
0x18006e901  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18006e906  nop
0x18006e907  mov     rcx, [rsp+38h+Str]; bstrString
0x18006e90c  call    cs:__imp_SysFreeString
0x18006e912  mov     eax, edi
0x18006e914  mov     rbp, [rsp+38h+arg_0]
0x18006e919  mov     rsi, [rsp+38h+arg_8]
0x18006e91e  add     rsp, 30h
0x18006e922  pop     rdi
0x18006e923  retn
```
