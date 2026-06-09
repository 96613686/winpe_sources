# TaskXmlReader::SetErrorInfoXmlLite(long)

- ea: `0x1800205cc`
- end: `0x180020728`
- name: `?SetErrorInfoXmlLite@TaskXmlReader@@AEAAJJ@Z`
- size: `348`
- prototype: `__int64 __fastcall(TaskXmlReader *__hidden this, int)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800036b4`
- `0x18001d2a8`
- `0x18001d7dc`
- `0x18001ed50`
- `0x18001f380`
- `0x180020118`
- `0x180020730`
- `0x180020988`

## callees

- `0x180020338`
- `0x1800205cc`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020690`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020690`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002065c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002065c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020678`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020678`

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
    if ( a2 == dword_180054130[2 * i] )
    {
      v5 = dword_180054134[2 * i];
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
    if ( a2 == dword_18004CDD0[4 * j] )
      break;
  }
  v6 = (&off_18004CDD8)[2 * j];
  if ( v6 )
    goto LABEL_14;
LABEL_18:
  LODWORD(v8) = 0;
  return TaskXmlReader::SetErrorInfo(this, -2147216614, 0, 0, v6, v8);
}

```

## disassembly

```asm
0x1800205cc  mov     [rsp+arg_8], rbx
0x1800205d1  mov     [rsp+arg_10], rbp
0x1800205d6  push    rsi
0x1800205d7  push    rdi
0x1800205d8  push    r14
0x1800205da  sub     rsp, 250h
0x1800205e1  mov     rax, cs:__security_cookie
0x1800205e8  xor     rax, rsp
0x1800205eb  mov     [rsp+268h+var_28], rax
0x1800205f3  mov     esi, edx
0x1800205f5  mov     rbp, rcx
0x1800205f8  cmp     edx, 0C00CEE00h
0x1800205fe  jl      loc_1800206EA
0x180020604  cmp     edx, 0C00CEFFFh
0x18002060a  jg      loc_1800206EA
0x180020610  xor     edx, edx; Val
0x180020612  lea     rcx, [rsp+268h+Buffer]; void *
0x180020617  mov     r8d, 200h; Size
0x18002061d  call    memset_0
0x180020622  xor     ebx, ebx
0x180020624  lea     r14, __ImageBase
0x18002062b  mov     eax, ebx
0x18002062d  cmp     eax, 3Ch ; '<'
0x180020630  jnb     short loc_18002069B
0x180020632  mov     ecx, eax
0x180020634  cmp     esi, ds:rva dword_180054130[r14+rcx*8]
0x18002063c  jz      short loc_180020642
0x18002063e  inc     eax
0x180020640  jmp     short loc_18002062D
0x180020642  mov     edi, ds:rva dword_180054134[r14+rcx*8]
0x18002064a  lea     r8, [rsp+268h+phModule]; phModule
0x18002064f  mov     ecx, 4; dwFlags
0x180020654  mov     [rsp+268h+phModule], rbx
0x180020659  mov     rdx, r14; lpModuleName
0x18002065c  call    cs:__imp_GetModuleHandleExW
0x180020662  test    eax, eax
0x180020664  jz      short loc_18002069B
0x180020666  mov     rcx, [rsp+268h+phModule]; hInstance
0x18002066b  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180020670  mov     r9d, 100h; cchBufferMax
0x180020676  mov     edx, edi; uID
0x180020678  call    cs:__imp_LoadStringW
0x18002067e  mov     rcx, [rsp+268h+phModule]; hLibModule
0x180020683  neg     eax
0x180020685  lea     rax, [rsp+268h+Buffer]
0x18002068a  sbb     rdi, rdi
0x18002068d  and     rdi, rax
0x180020690  call    cs:__imp_FreeLibrary
0x180020696  test    rdi, rdi
0x180020699  jnz     short loc_1800206C2
0x18002069b  mov     eax, ebx
0x18002069d  cmp     eax, 3Ch ; '<'
0x1800206a0  jnb     short loc_1800206D1
0x1800206a2  mov     edi, eax
0x1800206a4  add     rdi, rdi
0x1800206a7  cmp     esi, ds:rva dword_18004CDD0[r14+rdi*8]
0x1800206af  jz      short loc_1800206B5
0x1800206b1  inc     eax
0x1800206b3  jmp     short loc_18002069D
0x1800206b5  mov     rdi, ds:rva off_18004CDD8[r14+rdi*8]; "ERROR: unexpected end of input" ...
0x1800206bd  test    rdi, rdi
0x1800206c0  jz      short loc_1800206D4
0x1800206c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800206c6  inc     rax
0x1800206c9  cmp     [rdi+rax*2], bx
0x1800206cd  jnz     short loc_1800206C6
0x1800206cf  jmp     short loc_1800206D7
0x1800206d1  mov     rdi, rbx
0x1800206d4  mov     rax, rbx
0x1800206d7  mov     [rsp+268h+var_240], eax
0x1800206db  mov     edx, 8004131Ah; int
0x1800206e0  mov     [rsp+268h+var_248], rdi
0x1800206e5  mov     rcx, rbp; this
0x1800206e8  jmp     short loc_1800206F5
0x1800206ea  xor     ebx, ebx
0x1800206ec  mov     [rsp+268h+var_240], ebx; unsigned int
0x1800206f0  mov     [rsp+268h+var_248], rbx; unsigned __int16 *
0x1800206f5  xor     r9d, r9d; unsigned int
0x1800206f8  xor     r8d, r8d; unsigned __int16 *
0x1800206fb  call    ?SetErrorInfo@TaskXmlReader@@AEAAJJPEBGK0K@Z; TaskXmlReader::SetErrorInfo(long,ushort const *,ulong,ushort const *,ulong)
0x180020700  mov     rcx, [rsp+268h+var_28]
0x180020708  xor     rcx, rsp; StackCookie
0x18002070b  call    __security_check_cookie
0x180020710  lea     r11, [rsp+268h+var_18]
0x180020718  mov     rbx, [r11+28h]
0x18002071c  mov     rbp, [r11+30h]
0x180020720  mov     rsp, r11
0x180020723  pop     r14
0x180020725  pop     rdi
0x180020726  pop     rsi
0x180020727  retn
```
