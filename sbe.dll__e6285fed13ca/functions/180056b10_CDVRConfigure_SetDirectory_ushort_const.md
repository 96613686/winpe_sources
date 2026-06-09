# CDVRConfigure::SetDirectory(ushort const *)

- ea: `0x180056b10`
- end: `0x180056cf8`
- name: `?SetDirectory@CDVRConfigure@@UEAAJPEBG@Z`
- size: `488`
- prototype: `int(CDVRConfigure *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x180001c00`
- `0x1800021a0`
- `0x180002ed4`
- `0x18000624c`
- `0x180055d7c`
- `0x180055f84`
- `0x180056b10`
- `0x18005fbec`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180056b4f`
- `KERNEL32!LeaveCriticalSection` at `0x180056b4f`
- `KERNEL32!EnterCriticalSection` at `0x180056b3b`
- `KERNEL32!EnterCriticalSection` at `0x180056b3b`
- `KERNEL32!GetLastError` at `0x180056cc4`
- `KERNEL32!GetLastError` at `0x180056cc4`
- `KERNEL32!SetFileAttributesW` at `0x180056cba`
- `KERNEL32!SetFileAttributesW` at `0x180056cba`
- `KERNEL32!lstrlenW` at `0x180056b8b`
- `KERNEL32!lstrlenW` at `0x180056b8b`

## string_xrefs

- `0x180056bc4`: `TempSBE`

## pseudocode

```c
__int64 __fastcall CDVRConfigure::SetDirectory(CDVRConfigure *this, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rsi
  int *v9; // rax
  signed int LeafDirectory; // eax
  bool v11; // cc
  __int64 v12; // rdx
  void **v13; // r8
  int v14; // ecx
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // r8
  WCHAR FileName[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR v18[264]; // [rsp+240h] [rbp-238h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( a2 )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v6 = lstrlenW(a2);
      if ( v6 && (v7 = (unsigned int)(v6 - 1), v8 = (unsigned int)(a2[v7] != 92) + v6, (unsigned int)(v8 + 8) <= 0x104) )
      {
        v9 = (int *)L"\\";
        if ( a2[v7] == 92 )
          v9 = &dword_1800C6194;
        v4 = StringCchPrintfW(FileName, 0x104u, L"%s%s%s", a2, v9, L"TempSBE");
        if ( v4 >= 0 )
        {
          v4 = StringCchCopyW(v18, 0x104u, FileName);
          if ( v4 >= 0 )
          {
            if ( (unsigned __int64)(2 * v8) >= 0x208 )
              _report_rangecheckfailure();
            v18[v8] = 0;
            LeafDirectory = CreateLeafDirectory(v18);
            v4 = LeafDirectory;
            v11 = LeafDirectory <= 0;
            if ( !LeafDirectory )
            {
              LeafDirectory = CreateLeafDirectory(FileName);
              v4 = LeafDirectory;
              v11 = LeafDirectory <= 0;
              if ( !LeafDirectory )
              {
                v12 = *((_QWORD *)this + 8);
                if ( v12 )
                {
                  v13 = (void **)((*(_QWORD *)(v12 + 16) + 8LL) & -(__int64)(*(_QWORD *)(v12 + 16) != 0));
                  v14 = *(_DWORD *)(v12 + 24);
                  LODWORD(v12) = v14 - 1;
                  if ( !v14 )
                    LODWORD(v12) = 0;
                }
                else
                {
                  v13 = 0;
                }
                LeafDirectory = ACLTempBackingStoreDir(FileName, v12, v13);
                v4 = LeafDirectory;
                v11 = LeafDirectory <= 0;
                if ( !LeafDirectory )
                {
                  if ( SetFileAttributesW(FileName, 6u) )
                  {
                    v4 = !SetRegStringValW(*((HKEY *)this + 2), v15, v16, (const BYTE *)v18) ? 0x80004005 : 0;
                    goto LABEL_3;
                  }
                  LeafDirectory = GetLastError();
                  v4 = LeafDirectory;
                  v11 = LeafDirectory <= 0;
                }
              }
            }
            if ( !v11 )
              v4 = (unsigned __int16)LeafDirectory | 0x80070000;
          }
        }
      }
      else
      {
        v4 = -2147024809;
      }
    }
    else
    {
      v4 = -2147418113;
    }
  }
  else
  {
    v4 = -2147467261;
  }
LABEL_3:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180056b10  mov     [rsp+arg_10], rbx
0x180056b15  push    rbp
0x180056b16  push    rsi
0x180056b17  push    rdi
0x180056b18  sub     rsp, 460h
0x180056b1f  mov     rax, cs:__security_cookie
0x180056b26  xor     rax, rsp
0x180056b29  mov     [rsp+478h+var_28], rax
0x180056b31  mov     rdi, rcx
0x180056b34  mov     rbx, rdx
0x180056b37  add     rcx, 18h; lpCriticalSection
0x180056b3b  call    cs:__imp_EnterCriticalSection
0x180056b41  test    rbx, rbx
0x180056b44  jnz     short loc_180056B7A
0x180056b46  mov     ebx, 80004003h
0x180056b4b  lea     rcx, [rdi+18h]; lpCriticalSection
0x180056b4f  call    cs:__imp_LeaveCriticalSection
0x180056b55  mov     eax, ebx
0x180056b57  mov     rcx, [rsp+478h+var_28]
0x180056b5f  xor     rcx, rsp; StackCookie
0x180056b62  call    __security_check_cookie
0x180056b67  mov     rbx, [rsp+478h+arg_10]
0x180056b6f  add     rsp, 460h
0x180056b76  pop     rdi
0x180056b77  pop     rsi
0x180056b78  pop     rbp
0x180056b79  retn
0x180056b7a  cmp     qword ptr [rdi+10h], 0
0x180056b7f  jnz     short loc_180056B88
0x180056b81  mov     ebx, 8000FFFFh
0x180056b86  jmp     short loc_180056B4B
0x180056b88  mov     rcx, rbx; lpString
0x180056b8b  call    cs:__imp_lstrlenW
0x180056b91  mov     edx, eax
0x180056b93  test    eax, eax
0x180056b95  jnz     short loc_180056B9E
0x180056b97  mov     ebx, 80070057h
0x180056b9c  jmp     short loc_180056B4B
0x180056b9e  lea     ecx, [rax-1]
0x180056ba1  xor     eax, eax
0x180056ba3  cmp     word ptr [rbx+rcx*2], 5Ch ; '\'
0x180056ba8  setnz   al
0x180056bab  lea     esi, [rax+rdx]
0x180056bae  lea     eax, [rsi+8]
0x180056bb1  cmp     eax, 104h
0x180056bb6  ja      short loc_180056B97
0x180056bb8  cmp     word ptr [rbx+rcx*2], 5Ch ; '\'
0x180056bbd  lea     r8, dword_1800C6194
0x180056bc4  lea     rcx, aTempsbe; "TempSBE"
0x180056bcb  mov     r9, rbx
0x180056bce  mov     [rsp+478h+var_450], rcx
0x180056bd3  lea     rax, asc_1800C448C; "\\"
0x180056bda  cmovz   rax, r8
0x180056bde  lea     rcx, [rsp+478h+FileName]; Buffer
0x180056be3  lea     r8, aSSS; "%s%s%s"
0x180056bea  mov     [rsp+478h+var_458], rax
0x180056bef  mov     edx, 104h; unsigned __int64
0x180056bf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056bf9  mov     ebx, eax
0x180056bfb  test    eax, eax
0x180056bfd  js      loc_180056B4B
0x180056c03  lea     r8, [rsp+478h+FileName]; unsigned __int16 *
0x180056c08  mov     edx, 104h; unsigned __int64
0x180056c0d  lea     rcx, [rsp+478h+var_238]; unsigned __int16 *
0x180056c15  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056c1a  mov     ebx, eax
0x180056c1c  test    eax, eax
0x180056c1e  js      loc_180056B4B
0x180056c24  lea     rcx, [rsi+rsi]
0x180056c28  cmp     rcx, 208h
0x180056c2f  jnb     loc_180056CF2
0x180056c35  xor     eax, eax
0x180056c37  mov     [rsp+rcx+478h+var_238], ax
0x180056c3f  lea     rcx, [rsp+478h+var_238]; lpFileName
0x180056c47  call    CreateLeafDirectory
0x180056c4c  mov     ebx, eax
0x180056c4e  test    eax, eax
0x180056c50  jz      short loc_180056C66
0x180056c52  jle     loc_180056B4B
0x180056c58  movzx   ebx, ax
0x180056c5b  or      ebx, 80070000h
0x180056c61  jmp     loc_180056B4B
0x180056c66  lea     rcx, [rsp+478h+FileName]; lpFileName
0x180056c6b  call    CreateLeafDirectory
0x180056c70  mov     ebx, eax
0x180056c72  test    eax, eax
0x180056c74  jnz     short loc_180056C52
0x180056c76  mov     rdx, [rdi+40h]; unsigned int
0x180056c7a  test    rdx, rdx
0x180056c7d  jz      short loc_180056C9F
0x180056c7f  mov     rax, [rdx+10h]
0x180056c83  lea     rcx, [rax+8]
0x180056c87  neg     rax
0x180056c8a  sbb     r8, r8
0x180056c8d  xor     eax, eax
0x180056c8f  and     r8, rcx
0x180056c92  mov     ecx, [rdx+18h]
0x180056c95  test    ecx, ecx
0x180056c97  lea     edx, [rcx-1]
0x180056c9a  cmovz   edx, eax
0x180056c9d  jmp     short loc_180056CA2
0x180056c9f  xor     r8d, r8d; void **
0x180056ca2  lea     rcx, [rsp+478h+FileName]; pObjectName
0x180056ca7  call    ACLTempBackingStoreDir
0x180056cac  mov     ebx, eax
0x180056cae  test    eax, eax
0x180056cb0  jnz     short loc_180056C52
0x180056cb2  lea     edx, [rax+6]; dwFileAttributes
0x180056cb5  lea     rcx, [rsp+478h+FileName]; lpFileName
0x180056cba  call    cs:__imp_SetFileAttributesW
0x180056cc0  test    eax, eax
0x180056cc2  jnz     short loc_180056CD0
0x180056cc4  call    cs:__imp_GetLastError
0x180056cca  mov     ebx, eax
0x180056ccc  test    eax, eax
0x180056cce  jmp     short loc_180056C52
0x180056cd0  mov     rcx, [rdi+10h]; HKEY
0x180056cd4  lea     r9, [rsp+478h+var_238]; unsigned __int16 *
0x180056cdc  call    ?SetRegStringValW@@YAHPEAUHKEY__@@PEBG11@Z; SetRegStringValW(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180056ce1  neg     eax
0x180056ce3  sbb     ebx, ebx
0x180056ce5  not     ebx
0x180056ce7  and     ebx, 80004005h
0x180056ced  jmp     loc_180056B4B
0x180056cf2  call    __report_rangecheckfailure
```
