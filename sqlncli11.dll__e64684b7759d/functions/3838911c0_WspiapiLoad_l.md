# WspiapiLoad_l

- ea: `0x3838911c0`
- end: `0x383891373`
- name: `WspiapiLoad_l`
- size: `435`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x38387cad0`
- `0x3838833d0`
- `0x38388cce0`
- `0x38388d580`
- `0x383ab3130`
- `0x383ab3f80`
- `0x383ad83d0`

## callees

- `0x3838434c0`
- `0x3838911c0`

## import_xrefs

- `MSVCR100!strcat_s` at `0x38389128d`
- `MSVCR100!strcat_s` at `0x3838fdf2c`
- `MSVCR100!strcat_s` at `0x38389128d`
- `MSVCR100!strcat_s` at `0x3838fdf2c`
- `MSVCR100!strcpy_s` at `0x383891276`
- `MSVCR100!strcpy_s` at `0x3838fdf15`
- `MSVCR100!strcpy_s` at `0x383891276`
- `MSVCR100!strcpy_s` at `0x3838fdf15`
- `KERNEL32!FreeLibrary` at `0x3838fdefd`
- `KERNEL32!FreeLibrary` at `0x3838fdf61`
- `KERNEL32!FreeLibrary` at `0x3838fdf6f`
- `KERNEL32!FreeLibrary` at `0x3838fdefd`
- `KERNEL32!FreeLibrary` at `0x3838fdf61`
- `KERNEL32!FreeLibrary` at `0x3838fdf6f`
- `KERNEL32!GetProcAddress` at `0x3838912b0`
- `KERNEL32!GetProcAddress` at `0x3838912d5`
- `KERNEL32!GetProcAddress` at `0x3838fdf4f`
- `KERNEL32!GetProcAddress` at `0x3838912b0`
- `KERNEL32!GetProcAddress` at `0x3838912d5`
- `KERNEL32!GetProcAddress` at `0x3838fdf4f`
- `KERNEL32!GetSystemDirectoryA` at `0x38389124e`
- `KERNEL32!GetSystemDirectoryA` at `0x38389124e`
- `KERNEL32!LoadLibraryA` at `0x383891298`
- `KERNEL32!LoadLibraryA` at `0x3838fdf37`
- `KERNEL32!LoadLibraryA` at `0x383891298`
- `KERNEL32!LoadLibraryA` at `0x3838fdf37`

## pseudocode

```c
char *__fastcall WspiapiLoad_l(unsigned __int16 a1, _DWORD *a2)
{
  bool v2; // zf
  HMODULE LibraryA; // rax
  HMODULE v6; // rsi
  FARPROC *v7; // rbx
  int v8; // edi
  FARPROC ProcAddress; // rax
  HMODULE v11; // rax
  const CHAR *v12; // [rsp+20h] [rbp-278h]
  _QWORD v13[2]; // [rsp+28h] [rbp-270h] BYREF
  void *v14; // [rsp+38h] [rbp-260h]
  const char *v15; // [rsp+40h] [rbp-258h]
  void (__stdcall *v16)(struct addrinfo *); // [rsp+48h] [rbp-250h]
  char Destination[272]; // [rsp+50h] [rbp-248h] BYREF
  CHAR Buffer[272]; // [rsp+160h] [rbp-138h] BYREF

  v2 = `WspiapiLoad_l'::`2'::bInitialized == 0;
  v13[0] = WspiapiLegacyGetAddrInfo_l;
  v13[1] = "getnameinfo";
  v14 = &WspiapiLegacyGetNameInfo_l;
  v12 = "getaddrinfo";
  v15 = "freeaddrinfo";
  v16 = WspiapiLegacyFreeAddrInfo;
  *a2 = `WspiapiLoad_l'::`2'::bNeedslocale;
  if ( v2 )
  {
    if ( GetSystemDirectoryA(Buffer, 0x104u) )
    {
      strcpy_s(Destination, 0x10Cu, Buffer);
      strcat_s(Destination, 0x10Cu, "\\ws2_32");
      LibraryA = LoadLibraryA(Destination);
      v6 = LibraryA;
      if ( LibraryA )
      {
        if ( GetProcAddress(LibraryA, "getaddrinfo") )
          goto LABEL_5;
        FreeLibrary(v6);
      }
      strcpy_s(Destination, 0x10Cu, Buffer);
      strcat_s(Destination, 0x10Cu, "\\wship6");
      v11 = LoadLibraryA(Destination);
      v6 = v11;
      if ( v11 )
      {
        if ( GetProcAddress(v11, "getaddrinfo") )
        {
LABEL_5:
          v7 = (FARPROC *)v13;
          v8 = 0;
          while ( 1 )
          {
            ProcAddress = GetProcAddress(v6, (LPCSTR)*(v7 - 1));
            *v7 = ProcAddress;
            if ( !ProcAddress )
              break;
            ++v8;
            v7 += 2;
            if ( v8 >= 3 )
            {
              `WspiapiLoad_l'::`2'::bNeedslocale = 0;
              off_383B23980 = (__int64 (__usercall *)@<rax>(char *@<rcx>, char *@<rdx>, _locale_t))v13[0];
              off_383B23990 = v14;
              off_383B239A0 = (__int64 (__fastcall *)(void *))v16;
              goto LABEL_9;
            }
          }
          FreeLibrary(v6);
          goto LABEL_9;
        }
        FreeLibrary(v6);
      }
    }
LABEL_9:
    `WspiapiLoad_l'::`2'::bInitialized = 1;
    *a2 = `WspiapiLoad_l'::`2'::bNeedslocale;
  }
  return (&`WspiapiLoad_l'::`2'::rgtGlobal)[2 * a1 + 1];
}

```

## disassembly

```asm
0x3838911c0  push    rbx
0x3838911c2  push    rbp
0x3838911c3  push    r14
0x3838911c5  sub     rsp, 280h
0x3838911cc  mov     rax, cs:__security_cookie
0x3838911d3  xor     rax, rsp
0x3838911d6  mov     [rsp+298h+var_28], rax
0x3838911de  cmp     cs:?bInitialized@?1??WspiapiLoad_l@@9@4HA, 0; int `WspiapiLoad_l'::`2'::bInitialized
0x3838911e5  lea     rax, WspiapiLegacyGetAddrInfo_l
0x3838911ec  lea     rbx, aGetaddrinfo; "getaddrinfo"
0x3838911f3  mov     [rsp+298h+var_270], rax
0x3838911f8  lea     rax, aGetnameinfo; "getnameinfo"
0x3838911ff  mov     r14, rdx
0x383891202  mov     [rsp+298h+var_268], rax
0x383891207  lea     rax, WspiapiLegacyGetNameInfo_l
0x38389120e  movzx   ebp, cx
0x383891211  mov     [rsp+298h+var_260], rax
0x383891216  lea     rax, aFreeaddrinfo; "freeaddrinfo"
0x38389121d  mov     [rsp+298h+var_278], rbx
0x383891222  mov     [rsp+298h+var_258], rax
0x383891227  lea     rax, WspiapiLegacyFreeAddrInfo
0x38389122e  mov     [rsp+298h+var_250], rax
0x383891233  mov     eax, cs:?bNeedslocale@?1??WspiapiLoad_l@@9@4HA; int `WspiapiLoad_l'::`2'::bNeedslocale
0x383891239  mov     [rdx], eax
0x38389123b  jnz     loc_383891345
0x383891241  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x383891249  mov     edx, 104h; uSize
0x38389124e  call    cs:__imp_GetSystemDirectoryA
0x383891254  test    eax, eax
0x383891256  jz      loc_383891332
0x38389125c  lea     r8, [rsp+298h+Buffer]; Source
0x383891264  lea     rcx, [rsp+298h+Destination]; Destination
0x383891269  mov     edx, 10Ch; SizeInBytes
0x38389126e  mov     [rsp+298h+arg_0], rsi
0x383891276  call    cs:__imp_strcpy_s
0x38389127c  lea     r8, aWs232; "\\ws2_32"
0x383891283  lea     rcx, [rsp+298h+Destination]; Destination
0x383891288  mov     edx, 10Ch; SizeInBytes
0x38389128d  call    cs:__imp_strcat_s
0x383891293  lea     rcx, [rsp+298h+Destination]; lpLibFileName
0x383891298  call    cs:__imp_LoadLibraryA
0x38389129e  mov     rsi, rax
0x3838912a1  test    rax, rax
0x3838912a4  jz      loc_3838FDF03
0x3838912aa  mov     rdx, rbx; lpProcName
0x3838912ad  mov     rcx, rax; hModule
0x3838912b0  call    cs:__imp_GetProcAddress
0x3838912b6  test    rax, rax
0x3838912b9  jz      loc_3838FDEFA
0x3838912bf  mov     [rsp+298h+arg_10], rdi
0x3838912c7  lea     rbx, [rsp+298h+var_270]
0x3838912cc  xor     edi, edi
0x3838912ce  mov     rdx, [rbx-8]; lpProcName
0x3838912d2  mov     rcx, rsi; hModule
0x3838912d5  call    cs:__imp_GetProcAddress
0x3838912db  mov     [rbx], rax
0x3838912de  test    rax, rax
0x3838912e1  jz      loc_3838FDF6C
0x3838912e7  inc     edi
0x3838912e9  add     rbx, 10h
0x3838912ed  cmp     edi, 3
0x3838912f0  jl      short loc_3838912CE
0x3838912f2  mov     rax, [rsp+298h+var_270]
0x3838912f7  mov     cs:?bNeedslocale@?1??WspiapiLoad_l@@9@4HA, 0; int `WspiapiLoad_l'::`2'::bNeedslocale
0x383891301  mov     cs:off_383B23980, rax
0x383891308  mov     rax, [rsp+298h+var_260]
0x38389130d  mov     cs:off_383B23990, rax
0x383891314  mov     rax, [rsp+298h+var_250]
0x383891319  mov     cs:off_383B239A0, rax
0x383891320  jmp     short $+2
0x383891322  mov     rdi, [rsp+298h+arg_10]
0x38389132a  mov     rsi, [rsp+298h+arg_0]
0x383891332  mov     eax, cs:?bNeedslocale@?1??WspiapiLoad_l@@9@4HA; int `WspiapiLoad_l'::`2'::bNeedslocale
0x383891338  mov     cs:?bInitialized@?1??WspiapiLoad_l@@9@4HA, 1; int `WspiapiLoad_l'::`2'::bInitialized
0x383891342  mov     [r14], eax
0x383891345  movzx   eax, bp
0x383891348  lea     rcx, ?rgtGlobal@?1??WspiapiLoad_l@@9@4PAUWSPIAPI_FUNCTION@@A; WSPIAPI_FUNCTION near * `WspiapiLoad_l'::`2'::rgtGlobal
0x38389134f  add     rax, rax
0x383891352  mov     rax, [rcx+rax*8+8]
0x383891357  mov     rcx, [rsp+298h+var_28]
0x38389135f  xor     rcx, rsp; StackCookie
0x383891362  call    __security_check_cookie
0x383891367  add     rsp, 280h
0x38389136e  pop     r14
0x383891370  pop     rbp
0x383891371  pop     rbx
0x383891372  retn
0x3838fdefa  mov     rcx, rsi; hLibModule
0x3838fdefd  call    cs:__imp_FreeLibrary
0x3838fdf03  lea     r8, [rsp+298h+Buffer]; Source
0x3838fdf0b  lea     rcx, [rsp+298h+Destination]; Destination
0x3838fdf10  mov     edx, 10Ch; SizeInBytes
0x3838fdf15  call    cs:__imp_strcpy_s
0x3838fdf1b  lea     r8, aWship6; "\\wship6"
0x3838fdf22  lea     rcx, [rsp+298h+Destination]; Destination
0x3838fdf27  mov     edx, 10Ch; SizeInBytes
0x3838fdf2c  call    cs:__imp_strcat_s
0x3838fdf32  lea     rcx, [rsp+298h+Destination]; lpLibFileName
0x3838fdf37  call    cs:__imp_LoadLibraryA
0x3838fdf3d  mov     rsi, rax
0x3838fdf40  test    rax, rax
0x3838fdf43  jz      loc_38389132A
0x3838fdf49  mov     rdx, rbx; lpProcName
0x3838fdf4c  mov     rcx, rax; hModule
0x3838fdf4f  call    cs:__imp_GetProcAddress
0x3838fdf55  test    rax, rax
0x3838fdf58  jnz     loc_3838912BF
0x3838fdf5e  mov     rcx, rsi; hLibModule
0x3838fdf61  call    cs:__imp_FreeLibrary
0x3838fdf67  jmp     loc_38389132A
0x3838fdf6c  mov     rcx, rsi; hLibModule
0x3838fdf6f  call    cs:__imp_FreeLibrary
0x3838fdf75  nop
0x3838fdf76  jmp     loc_383891322
```
