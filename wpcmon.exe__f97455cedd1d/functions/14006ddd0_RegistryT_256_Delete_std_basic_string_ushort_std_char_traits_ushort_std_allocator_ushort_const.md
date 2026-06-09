# RegistryT<256>::Delete(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14006ddd0`
- end: `0x14006df17`
- name: `?Delete@?$RegistryT@$0BAA@@@UEAAAEAV1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x140006338`
- `0x14001c804`
- `0x140060e60`
- `0x140060f58`
- `0x14006ddd0`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x14006ddfd`
- `ADVAPI32!RegDeleteTreeW` at `0x14006ddfd`
- `ADVAPI32!RegDeleteValueW` at `0x14006de23`
- `ADVAPI32!RegDeleteValueW` at `0x14006de23`

## pseudocode

```c
__int64 __fastcall RegistryT<256>::Delete(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  LSTATUS v4; // eax
  unsigned int v5; // edi
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  __int64 v11; // r10
  int v12; // eax
  __int64 v13; // r10
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  v2 = a2;
  if ( *((_QWORD *)a2 + 2) < 0x100u )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    v4 = RegDeleteTreeW(*(HKEY *)(a1 + 16), a2);
    v5 = v4;
    if ( (v4 & 0xFFFFFFFD) != 0 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v12 = std::wstring::c_str(v2);
        WPP_SF_Sd(*(_QWORD *)(v13 + 16), 16, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v12, v5);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  if ( *((_QWORD *)v2 + 3) <= 7u )
    v6 = v2;
  else
    v6 = *(const WCHAR **)v2;
  v7 = RegDeleteValueW(*(HKEY *)(a1 + 16), v6);
  v8 = v7;
  if ( (v7 & 0xFFFFFFFD) != 0 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = std::wstring::c_str(v2);
      WPP_SF_Sd(*(_QWORD *)(v11 + 16), 17, (unsigned int)WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v10, v8);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x14006ddd0  mov     [rsp+arg_0], rbx
0x14006ddd5  mov     [rsp+arg_8], rsi
0x14006ddda  push    rdi
0x14006dddb  sub     rsp, 60h
0x14006dddf  cmp     qword ptr [rdx+10h], 100h
0x14006dde7  mov     rbx, rdx
0x14006ddea  mov     rsi, rcx
0x14006dded  jnb     short loc_14006DE10
0x14006ddef  cmp     qword ptr [rdx+18h], 7
0x14006ddf4  jbe     short loc_14006DDF9
0x14006ddf6  mov     rdx, [rdx]; lpSubKey
0x14006ddf9  mov     rcx, [rcx+10h]; hKey
0x14006ddfd  call    cs:__imp_RegDeleteTreeW
0x14006de03  mov     edi, eax
0x14006de05  test    eax, 0FFFFFFFDh
0x14006de0a  jnz     loc_14006DEAE
0x14006de10  cmp     qword ptr [rbx+18h], 7
0x14006de15  jbe     short loc_14006DE1C
0x14006de17  mov     rdx, [rbx]
0x14006de1a  jmp     short loc_14006DE1F
0x14006de1c  mov     rdx, rbx; lpValueName
0x14006de1f  mov     rcx, [rsi+10h]; hKey
0x14006de23  call    cs:__imp_RegDeleteValueW
0x14006de29  mov     edi, eax
0x14006de2b  test    eax, 0FFFFFFFDh
0x14006de30  jnz     short loc_14006DE45
0x14006de32  mov     rbx, [rsp+68h+arg_0]
0x14006de37  mov     rax, rsi
0x14006de3a  mov     rsi, [rsp+68h+arg_8]
0x14006de3f  add     rsp, 60h
0x14006de43  pop     rdi
0x14006de44  retn
0x14006de45  test    eax, eax
0x14006de47  jle     short loc_14006DE52
0x14006de49  movzx   edi, ax
0x14006de4c  or      edi, 80070000h
0x14006de52  mov     r10, cs:WPP_GLOBAL_Control
0x14006de59  lea     rax, WPP_GLOBAL_Control
0x14006de60  cmp     r10, rax
0x14006de63  jz      short loc_14006DE90
0x14006de65  test    byte ptr [r10+1Ch], 1
0x14006de6a  jz      short loc_14006DE90
0x14006de6c  mov     rcx, rbx
0x14006de6f  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14006de74  mov     rcx, [r10+10h]
0x14006de78  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x14006de7f  mov     r9, rax
0x14006de82  mov     [rsp+68h+var_48], edi
0x14006de86  mov     edx, 11h
0x14006de8b  call    WPP_SF_Sd
0x14006de90  mov     edx, edi; int
0x14006de92  lea     rcx, [rsp+68h+pExceptionObject]; this
0x14006de97  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14006de9c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14006dea3  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14006dea8  call    _CxxThrowException_0
0x14006deae  test    eax, eax
0x14006deb0  jle     short loc_14006DEBB
0x14006deb2  movzx   edi, ax
0x14006deb5  or      edi, 80070000h
0x14006debb  mov     r10, cs:WPP_GLOBAL_Control
0x14006dec2  lea     rax, WPP_GLOBAL_Control
0x14006dec9  cmp     r10, rax
0x14006decc  jz      short loc_14006DEF9
0x14006dece  test    byte ptr [r10+1Ch], 1
0x14006ded3  jz      short loc_14006DEF9
0x14006ded5  mov     rcx, rbx
0x14006ded8  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14006dedd  mov     rcx, [r10+10h]
0x14006dee1  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x14006dee8  mov     r9, rax
0x14006deeb  mov     [rsp+68h+var_48], edi
0x14006deef  mov     edx, 10h
0x14006def4  call    WPP_SF_Sd
0x14006def9  mov     edx, edi; int
0x14006defb  lea     rcx, [rsp+68h+pExceptionObject]; this
0x14006df00  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14006df05  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14006df0c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14006df11  call    _CxxThrowException_0
```
