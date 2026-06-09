# TaskXmlReader::SetErrorInfoXmlLite(long)

- ea: `0x18003b514`
- end: `0x18003b683`
- name: `?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z`
- size: `367`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this, int)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800170a0`
- `0x180018940`
- `0x1800193f0`
- `0x180019730`
- `0x180019b50`
- `0x18001a460`
- `0x18001af90`
- `0x18004f638`

## callees

- `0x180019228`
- `0x18003b514`
- `0x18005260b`
- `0x180052640`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003b5a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003b5a4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b5e4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b5e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003b5c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003b5c6`

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
    if ( a2 == dword_18007E850[2 * i] )
    {
      v5 = dword_18007E854[2 * i];
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
    if ( a2 == dword_180077870[4 * j] )
      break;
  }
  v6 = (&off_180077878)[2 * j];
  if ( v6 )
    goto LABEL_14;
LABEL_18:
  LODWORD(v8) = 0;
  return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v6, v8);
}

```

## disassembly

```asm
0x18003b514  mov     [rsp+arg_8], rbx
0x18003b519  mov     [rsp+arg_10], rbp
0x18003b51e  push    rsi
0x18003b51f  push    rdi
0x18003b520  push    r14
0x18003b522  sub     rsp, 250h
0x18003b529  mov     rax, cs:__security_cookie
0x18003b530  xor     rax, rsp
0x18003b533  mov     [rsp+268h+var_28], rax
0x18003b53b  mov     esi, edx
0x18003b53d  mov     rbp, rcx
0x18003b540  cmp     edx, 0C00CEE00h
0x18003b546  jl      loc_18003B644
0x18003b54c  cmp     edx, 0C00CEFFFh
0x18003b552  jg      loc_18003B644
0x18003b558  xor     edx, edx; Val
0x18003b55a  lea     rcx, [rsp+268h+Buffer]; void *
0x18003b55f  mov     r8d, 200h; Size
0x18003b565  call    memset_0
0x18003b56a  xor     ebx, ebx
0x18003b56c  lea     r14, __ImageBase
0x18003b573  mov     eax, ebx
0x18003b575  cmp     eax, 3Ch ; '<'
0x18003b578  jnb     short loc_18003B5F5
0x18003b57a  mov     ecx, eax
0x18003b57c  cmp     esi, ds:rva dword_18007E850[r14+rcx*8]
0x18003b584  jz      short loc_18003B58A
0x18003b586  inc     eax
0x18003b588  jmp     short loc_18003B575
0x18003b58a  mov     edi, ds:rva dword_18007E854[r14+rcx*8]
0x18003b592  lea     r8, [rsp+268h+phModule]; phModule
0x18003b597  mov     ecx, 4; dwFlags
0x18003b59c  mov     [rsp+268h+phModule], rbx
0x18003b5a1  mov     rdx, r14; lpModuleName
0x18003b5a4  call    cs:__imp_GetModuleHandleExW
0x18003b5ab  nop     dword ptr [rax+rax+00h]
0x18003b5b0  test    eax, eax
0x18003b5b2  jz      short loc_18003B5F5
0x18003b5b4  mov     rcx, [rsp+268h+phModule]; hInstance
0x18003b5b9  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x18003b5be  mov     r9d, 100h; cchBufferMax
0x18003b5c4  mov     edx, edi; uID
0x18003b5c6  call    cs:__imp_LoadStringW
0x18003b5cd  nop     dword ptr [rax+rax+00h]
0x18003b5d2  mov     rcx, [rsp+268h+phModule]; hLibModule
0x18003b5d7  neg     eax
0x18003b5d9  lea     rax, [rsp+268h+Buffer]
0x18003b5de  sbb     rdi, rdi
0x18003b5e1  and     rdi, rax
0x18003b5e4  call    cs:__imp_FreeLibrary
0x18003b5eb  nop     dword ptr [rax+rax+00h]
0x18003b5f0  test    rdi, rdi
0x18003b5f3  jnz     short loc_18003B61C
0x18003b5f5  mov     eax, ebx
0x18003b5f7  cmp     eax, 3Ch ; '<'
0x18003b5fa  jnb     short loc_18003B62B
0x18003b5fc  mov     edi, eax
0x18003b5fe  add     rdi, rdi
0x18003b601  cmp     esi, ds:rva dword_180077870[r14+rdi*8]
0x18003b609  jz      short loc_18003B60F
0x18003b60b  inc     eax
0x18003b60d  jmp     short loc_18003B5F7
0x18003b60f  mov     rdi, ds:rva off_180077878[r14+rdi*8]; "ERROR: unexpected end of input" ...
0x18003b617  test    rdi, rdi
0x18003b61a  jz      short loc_18003B62E
0x18003b61c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b620  inc     rax
0x18003b623  cmp     [rdi+rax*2], bx
0x18003b627  jnz     short loc_18003B620
0x18003b629  jmp     short loc_18003B631
0x18003b62b  mov     rdi, rbx
0x18003b62e  mov     rax, rbx
0x18003b631  mov     [rsp+268h+var_240], eax
0x18003b635  mov     edx, 8004131Ah; int
0x18003b63a  mov     [rsp+268h+var_248], rdi
0x18003b63f  mov     rcx, rbp; this
0x18003b642  jmp     short loc_18003B64F
0x18003b644  xor     ebx, ebx
0x18003b646  mov     [rsp+268h+var_240], ebx; unsigned int
0x18003b64a  mov     [rsp+268h+var_248], rbx; unsigned __int16 *
0x18003b64f  xor     r9d, r9d; unsigned int
0x18003b652  xor     r8d, r8d; unsigned __int16 *
0x18003b655  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x18003b65a  mov     rcx, [rsp+268h+var_28]
0x18003b662  xor     rcx, rsp; StackCookie
0x18003b665  call    __security_check_cookie
0x18003b66a  lea     r11, [rsp+268h+var_18]
0x18003b672  mov     rbx, [r11+28h]
0x18003b676  mov     rbp, [r11+30h]
0x18003b67a  mov     rsp, r11
0x18003b67d  pop     r14
0x18003b67f  pop     rdi
0x18003b680  pop     rsi
0x18003b681  retn
```
