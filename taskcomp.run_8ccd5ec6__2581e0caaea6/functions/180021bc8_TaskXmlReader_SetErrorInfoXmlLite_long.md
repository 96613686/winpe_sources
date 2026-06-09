# TaskXmlReader::SetErrorInfoXmlLite(long)

- ea: `0x180021bc8`
- end: `0x180021d37`
- name: `?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z`
- size: `367`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this, int)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180003858`
- `0x18001e83c`
- `0x18001ed88`
- `0x18002033c`
- `0x18002096c`
- `0x180021710`
- `0x180021d40`
- `0x180021fa8`

## callees

- `0x180021934`
- `0x180021bc8`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021c98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021c98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180021c58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180021c58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021c7a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021c7a`

## pseudocode

```c
__int64 __fastcall TaskXmlReader::SetErrorInfoXmlLite(TaskXmlReader *this, int a2)
{
  unsigned int i; // eax
  UINT v5; // edi
  unsigned __int16 *v6; // rdi
  unsigned int j; // eax
  __int64 v8; // rax
  HMODULE phModule; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[256]; // [rsp+40h] [rbp-228h] BYREF

  if ( a2 < -1072894464 || a2 > -1072893953 )
    return TaskXmlReader::SetErrorInfo(this, a2, 0, 0, 0, 0);
  memset_0(Buffer, 0, sizeof(Buffer));
  for ( i = 0; i < 0x3C; ++i )
  {
    if ( a2 == dword_180056140[2 * i] )
    {
      v5 = dword_180056144[2 * i];
      phModule = 0;
      if ( GetModuleHandleExW(4u, &_ImageBase, &phModule) )
      {
        v6 = (unsigned __int16 *)((unsigned __int64)Buffer & -(__int64)(LoadStringW(phModule, v5, Buffer, 256) != 0));
        FreeLibrary(phModule);
        if ( v6 )
        {
LABEL_14:
          v8 = -1;
          do
            ++v8;
          while ( v6[v8] );
          return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v6, v8);
        }
      }
      break;
    }
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= 0x3C )
    {
      v6 = 0;
      goto LABEL_18;
    }
    if ( a2 == dword_18004EDD0[4 * j] )
      break;
  }
  v6 = (&off_18004EDD8)[2 * j];
  if ( v6 )
    goto LABEL_14;
LABEL_18:
  LODWORD(v8) = 0;
  return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v6, v8);
}

```

## disassembly

```asm
0x180021bc8  mov     [rsp+arg_8], rbx
0x180021bcd  mov     [rsp+arg_10], rbp
0x180021bd2  push    rsi
0x180021bd3  push    rdi
0x180021bd4  push    r14
0x180021bd6  sub     rsp, 250h
0x180021bdd  mov     rax, cs:__security_cookie
0x180021be4  xor     rax, rsp
0x180021be7  mov     [rsp+268h+var_28], rax
0x180021bef  mov     esi, edx
0x180021bf1  mov     rbp, rcx
0x180021bf4  cmp     edx, 0C00CEE00h
0x180021bfa  jl      loc_180021CF8
0x180021c00  cmp     edx, 0C00CEFFFh
0x180021c06  jg      loc_180021CF8
0x180021c0c  xor     edx, edx; Val
0x180021c0e  lea     rcx, [rsp+268h+Buffer]; void *
0x180021c13  mov     r8d, 200h; Size
0x180021c19  call    memset_0
0x180021c1e  xor     ebx, ebx
0x180021c20  lea     r14, __ImageBase
0x180021c27  mov     eax, ebx
0x180021c29  cmp     eax, 3Ch ; '<'
0x180021c2c  jnb     short loc_180021CA9
0x180021c2e  mov     ecx, eax
0x180021c30  cmp     esi, ds:rva dword_180056140[r14+rcx*8]
0x180021c38  jz      short loc_180021C3E
0x180021c3a  inc     eax
0x180021c3c  jmp     short loc_180021C29
0x180021c3e  mov     edi, ds:rva dword_180056144[r14+rcx*8]
0x180021c46  lea     r8, [rsp+268h+phModule]; phModule
0x180021c4b  mov     ecx, 4; dwFlags
0x180021c50  mov     [rsp+268h+phModule], rbx
0x180021c55  mov     rdx, r14; lpModuleName
0x180021c58  call    cs:__imp_GetModuleHandleExW
0x180021c5f  nop     dword ptr [rax+rax+00h]
0x180021c64  test    eax, eax
0x180021c66  jz      short loc_180021CA9
0x180021c68  mov     rcx, [rsp+268h+phModule]; hInstance
0x180021c6d  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180021c72  mov     r9d, 100h; cchBufferMax
0x180021c78  mov     edx, edi; uID
0x180021c7a  call    cs:__imp_LoadStringW
0x180021c81  nop     dword ptr [rax+rax+00h]
0x180021c86  mov     rcx, [rsp+268h+phModule]; hLibModule
0x180021c8b  neg     eax
0x180021c8d  lea     rax, [rsp+268h+Buffer]
0x180021c92  sbb     rdi, rdi
0x180021c95  and     rdi, rax
0x180021c98  call    cs:__imp_FreeLibrary
0x180021c9f  nop     dword ptr [rax+rax+00h]
0x180021ca4  test    rdi, rdi
0x180021ca7  jnz     short loc_180021CD0
0x180021ca9  mov     eax, ebx
0x180021cab  cmp     eax, 3Ch ; '<'
0x180021cae  jnb     short loc_180021CDF
0x180021cb0  mov     edi, eax
0x180021cb2  add     rdi, rdi
0x180021cb5  cmp     esi, ds:rva dword_18004EDD0[r14+rdi*8]
0x180021cbd  jz      short loc_180021CC3
0x180021cbf  inc     eax
0x180021cc1  jmp     short loc_180021CAB
0x180021cc3  mov     rdi, ds:rva off_18004EDD8[r14+rdi*8]; "ERROR: unexpected end of input" ...
0x180021ccb  test    rdi, rdi
0x180021cce  jz      short loc_180021CE2
0x180021cd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021cd4  inc     rax
0x180021cd7  cmp     [rdi+rax*2], bx
0x180021cdb  jnz     short loc_180021CD4
0x180021cdd  jmp     short loc_180021CE5
0x180021cdf  mov     rdi, rbx
0x180021ce2  mov     rax, rbx
0x180021ce5  mov     [rsp+268h+var_240], eax
0x180021ce9  mov     edx, 8004131Ah; int
0x180021cee  mov     [rsp+268h+var_248], rdi
0x180021cf3  mov     rcx, rbp; this
0x180021cf6  jmp     short loc_180021D03
0x180021cf8  xor     ebx, ebx
0x180021cfa  mov     [rsp+268h+var_240], ebx; unsigned int
0x180021cfe  mov     [rsp+268h+var_248], rbx; unsigned __int16 *
0x180021d03  xor     r9d, r9d; unsigned int
0x180021d06  xor     r8d, r8d; unsigned __int16 *
0x180021d09  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180021d0e  mov     rcx, [rsp+268h+var_28]
0x180021d16  xor     rcx, rsp; StackCookie
0x180021d19  call    __security_check_cookie
0x180021d1e  lea     r11, [rsp+268h+var_18]
0x180021d26  mov     rbx, [r11+28h]
0x180021d2a  mov     rbp, [r11+30h]
0x180021d2e  mov     rsp, r11
0x180021d31  pop     r14
0x180021d33  pop     rdi
0x180021d34  pop     rsi
0x180021d35  retn
```
