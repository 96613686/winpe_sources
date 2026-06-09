# TaskXmlReader::SetErrorInfoXmlLite(long)

- ea: `0x18003843c`
- end: `0x180038598`
- name: `?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z`
- size: `348`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this, int)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180015f60`
- `0x180017860`
- `0x1800182b0`
- `0x1800185f0`
- `0x180018a00`
- `0x1800192f0`
- `0x180019de0`
- `0x18004ba18`

## callees

- `0x1800180f0`
- `0x18003843c`
- `0x18004e90f`
- `0x18004e950`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800384cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800384cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038500`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038500`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800384e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800384e8`

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
    if ( a2 == dword_18007A870[2 * i] )
    {
      v5 = dword_18007A874[2 * i];
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
    if ( a2 == dword_180073890[4 * j] )
      break;
  }
  v6 = (&off_180073898)[2 * j];
  if ( v6 )
    goto LABEL_14;
LABEL_18:
  LODWORD(v8) = 0;
  return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v6, v8);
}

```

## disassembly

```asm
0x18003843c  mov     [rsp+arg_8], rbx
0x180038441  mov     [rsp+arg_10], rbp
0x180038446  push    rsi
0x180038447  push    rdi
0x180038448  push    r14
0x18003844a  sub     rsp, 250h
0x180038451  mov     rax, cs:__security_cookie
0x180038458  xor     rax, rsp
0x18003845b  mov     [rsp+268h+var_28], rax
0x180038463  mov     esi, edx
0x180038465  mov     rbp, rcx
0x180038468  cmp     edx, 0C00CEE00h
0x18003846e  jl      loc_18003855A
0x180038474  cmp     edx, 0C00CEFFFh
0x18003847a  jg      loc_18003855A
0x180038480  xor     edx, edx; Val
0x180038482  lea     rcx, [rsp+268h+Buffer]; void *
0x180038487  mov     r8d, 200h; Size
0x18003848d  call    memset_0
0x180038492  xor     ebx, ebx
0x180038494  lea     r14, __ImageBase
0x18003849b  mov     eax, ebx
0x18003849d  cmp     eax, 3Ch ; '<'
0x1800384a0  jnb     short loc_18003850B
0x1800384a2  mov     ecx, eax
0x1800384a4  cmp     esi, ds:rva dword_18007A870[r14+rcx*8]
0x1800384ac  jz      short loc_1800384B2
0x1800384ae  inc     eax
0x1800384b0  jmp     short loc_18003849D
0x1800384b2  mov     edi, ds:rva dword_18007A874[r14+rcx*8]
0x1800384ba  lea     r8, [rsp+268h+phModule]; phModule
0x1800384bf  mov     ecx, 4; dwFlags
0x1800384c4  mov     [rsp+268h+phModule], rbx
0x1800384c9  mov     rdx, r14; lpModuleName
0x1800384cc  call    cs:__imp_GetModuleHandleExW
0x1800384d2  test    eax, eax
0x1800384d4  jz      short loc_18003850B
0x1800384d6  mov     rcx, [rsp+268h+phModule]; hInstance
0x1800384db  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1800384e0  mov     r9d, 100h; cchBufferMax
0x1800384e6  mov     edx, edi; uID
0x1800384e8  call    cs:__imp_LoadStringW
0x1800384ee  mov     rcx, [rsp+268h+phModule]; hLibModule
0x1800384f3  neg     eax
0x1800384f5  lea     rax, [rsp+268h+Buffer]
0x1800384fa  sbb     rdi, rdi
0x1800384fd  and     rdi, rax
0x180038500  call    cs:__imp_FreeLibrary
0x180038506  test    rdi, rdi
0x180038509  jnz     short loc_180038532
0x18003850b  mov     eax, ebx
0x18003850d  cmp     eax, 3Ch ; '<'
0x180038510  jnb     short loc_180038541
0x180038512  mov     edi, eax
0x180038514  add     rdi, rdi
0x180038517  cmp     esi, ds:rva dword_180073890[r14+rdi*8]
0x18003851f  jz      short loc_180038525
0x180038521  inc     eax
0x180038523  jmp     short loc_18003850D
0x180038525  mov     rdi, ds:rva off_180073898[r14+rdi*8]; "ERROR: unexpected end of input" ...
0x18003852d  test    rdi, rdi
0x180038530  jz      short loc_180038544
0x180038532  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038536  inc     rax
0x180038539  cmp     [rdi+rax*2], bx
0x18003853d  jnz     short loc_180038536
0x18003853f  jmp     short loc_180038547
0x180038541  mov     rdi, rbx
0x180038544  mov     rax, rbx
0x180038547  mov     [rsp+268h+var_240], eax
0x18003854b  mov     edx, 8004131Ah; int
0x180038550  mov     [rsp+268h+var_248], rdi
0x180038555  mov     rcx, rbp; this
0x180038558  jmp     short loc_180038565
0x18003855a  xor     ebx, ebx
0x18003855c  mov     [rsp+268h+var_240], ebx; unsigned int
0x180038560  mov     [rsp+268h+var_248], rbx; unsigned __int16 *
0x180038565  xor     r9d, r9d; unsigned int
0x180038568  xor     r8d, r8d; unsigned __int16 *
0x18003856b  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180038570  mov     rcx, [rsp+268h+var_28]
0x180038578  xor     rcx, rsp; StackCookie
0x18003857b  call    __security_check_cookie
0x180038580  lea     r11, [rsp+268h+var_18]
0x180038588  mov     rbx, [r11+28h]
0x18003858c  mov     rbp, [r11+30h]
0x180038590  mov     rsp, r11
0x180038593  pop     r14
0x180038595  pop     rdi
0x180038596  pop     rsi
0x180038597  retn
```
