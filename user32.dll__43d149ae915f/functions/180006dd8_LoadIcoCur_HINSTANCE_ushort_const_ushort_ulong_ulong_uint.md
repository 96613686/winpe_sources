# LoadIcoCur(HINSTANCE__ *,ushort const *,ushort *,ulong,ulong,uint)

- ea: `0x180006dd8`
- end: `0x1800070da`
- name: `?LoadIcoCur@@YAPEAUHICON__@@PEAUHINSTANCE__@@PEBGPEAGKKI@Z`
- size: `770`
- prototype: `HICON __usercall@<rax>(HINSTANCE hModule@<rcx>, PCWSTR SourceString@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int)`
- caller_count: `22`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180002080`
- `0x180006140`
- `0x1800293a0`
- `0x18002aafc`
- `0x18002cd24`
- `0x18002d750`
- `0x18002d800`
- `0x18002d8f0`
- `0x18002eea4`
- `0x180054cb0`
- `0x1800558a0`
- `0x180055930`
- `0x18005af90`
- `0x18005ed68`
- `0x18005edc4`
- `0x18005fc80`
- `0x180067700`
- `0x18006fcb0`
- `0x180073910`
- `0x18007d2a0`
- `0x1800899fc`
- `0x18008f150`

## callees

- `0x180006dd8`
- `0x1800070e0`
- `0x180007640`
- `0x1800081d4`
- `0x180008324`
- `0x18001a2b8`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserFindExistingCursorIcon` at `0x180006fd4`
- `win32u!NtUserFindExistingCursorIcon` at `0x180006fd4`
- `win32u!NtUserGetThreadState` at `0x18000702e`
- `win32u!NtUserGetThreadState` at `0x18000702e`
- `ntdll!RtlInitUnicodeString` at `0x180006f9b`
- `ntdll!RtlInitUnicodeString` at `0x1800070ca`
- `ntdll!RtlInitUnicodeString` at `0x180006f9b`
- `ntdll!RtlInitUnicodeString` at `0x1800070ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180007053`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180007053`

## pseudocode

```c
__int64 __fastcall LoadIcoCur(
        __int64 *hModule,
        __int64 *SourceString,
        unsigned __int16 *a3,
        unsigned int DpiDependentMetric,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v7; // r15d
  unsigned int v9; // ebx
  unsigned __int64 v10; // r14
  HINSTANCE v11; // rsi
  WCHAR *v12; // rax
  int v13; // edi
  unsigned int DpiForSystem; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  HICON v17; // rax
  __int64 ExistingCursorIcon; // rdi
  struct _UNICODE_STRING *v20; // rdx
  int v21; // eax
  const WCHAR *SourceStringa; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v25; // [rsp+44h] [rbp-BCh]
  int v26; // [rsp+4Ch] [rbp-B4h]
  struct _UNICODE_STRING v27; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF

  v7 = a5;
  v9 = a6;
  v10 = (unsigned __int64)SourceString;
  v11 = (HINSTANCE)hModule;
  if ( !NtCurrentTeb()->Win32ThreadInfo && !NtUserGetThreadState(14) )
    return 0;
  if ( v11 )
  {
    if ( !GetModuleFileNameW(v11, Filename, 0x104u) )
      StringCchPrintfW(Filename, 0x104u, &qword_1800A8D38, v11);
    v12 = Filename;
  }
  else
  {
    v11 = hmodUser;
    v12 = (WCHAR *)&szUSER32;
  }
  SourceStringa = v12;
  if ( (a6 & 0x2000) != 0 )
    v9 = a6 & 0xFFFFD7FF | 0x800;
  if ( v11 == hmodUser && (v10 & 0xFFFFFFFFFFFF0000uLL) == 0 )
  {
    SourceString = qword_1800A89B8;
    hModule = &qword_1800A89B0;
    v21 = (a3 != (unsigned __int16 *)3) + 1;
    if ( a3 != (unsigned __int16 *)3 )
      hModule = qword_1800A89B8;
    while ( --v21 >= 0 )
    {
      if ( *(_WORD *)hModule == (_WORD)v10 )
      {
        if ( (*((_BYTE *)hModule + 4) & 1) == 0 || LODWORD(NtCurrentTeb()->Win32ClientInfo[2]) < 0x400 )
        {
          v10 = *((unsigned __int16 *)hModule + 1);
          break;
        }
        return 0;
      }
      hModule = (__int64 *)((char *)hModule + 6);
    }
  }
  if ( DpiDependentMetric )
  {
    v13 = v9 & 0x40;
  }
  else
  {
    v13 = v9 & 0x40;
    if ( (v9 & 0x40) != 0 )
    {
      DpiForSystem = GetDpiForSystem(hModule, SourceString);
      v15 = 5;
      if ( a3 != (unsigned __int16 *)3 )
        v15 = 7;
      DpiDependentMetric = GetDpiDependentMetric(v15, DpiForSystem);
    }
    else
    {
      DpiDependentMetric = 0;
    }
  }
  if ( !a5 )
  {
    if ( v13 )
    {
      v16 = GetDpiForSystem(hModule, SourceString);
      v7 = GetDpiDependentMetric((unsigned int)(a3 != (unsigned __int16 *)3) + 6, v16);
    }
    else
    {
      v7 = 0;
    }
  }
  if ( (v9 & 0x8000) == 0 )
    goto LABEL_17;
  v23 = 0;
  v24 = (int)a3;
  v26 = 0;
  v25 = v11 == hmodUser ? 0LL : __PAIR64__(v7, DpiDependentMetric);
  p_DestinationString = &DestinationString;
  *(_QWORD *)&DestinationString.Length = 0;
  v27 = 0;
  DestinationString.Buffer = 0;
  v28 = 0;
  v31 = 0;
  RtlInitUnicodeString(&DestinationString, SourceStringa);
  DWORD2(v28) = 0;
  v20 = &v27;
  *(_QWORD *)&v28 = &v27;
  if ( (v10 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    RtlInitUnicodeString(&v27, (PCWSTR)v10);
    v20 = (struct _UNICODE_STRING *)v28;
  }
  else
  {
    v27.Buffer = (PWSTR)v10;
    *(_DWORD *)&v27.Length = 0;
  }
  ExistingCursorIcon = NtUserFindExistingCursorIcon(p_DestinationString, v20, &v23);
  if ( !ExistingCursorIcon )
  {
LABEL_17:
    v17 = (HICON)ObjectFromDIBResource(v11, (const unsigned __int16 *)v10, a3, DpiDependentMetric, v7, v9);
    ExistingCursorIcon = (__int64)v17;
    if ( a3 == (unsigned __int16 *)1 )
      CreateDpiCursors(v17, v11, (const unsigned __int16 *)v10, DpiDependentMetric, v7, v9);
  }
  return ExistingCursorIcon;
}

```

## disassembly

```asm
0x180006dd8  push    rbp
0x180006dda  push    rbx
0x180006ddb  push    rsi
0x180006ddc  push    rdi
0x180006ddd  push    r12
0x180006ddf  push    r13
0x180006de1  push    r14
0x180006de3  push    r15
0x180006de5  lea     rbp, [rsp-1B8h]
0x180006ded  sub     rsp, 2B8h
0x180006df4  mov     rax, cs:__security_cookie
0x180006dfb  xor     rax, rsp
0x180006dfe  mov     [rbp+1F0h+var_50], rax
0x180006e05  mov     rax, gs:30h
0x180006e0e  mov     r12d, r9d
0x180006e11  mov     r15d, [rbp+1F0h+arg_20]
0x180006e18  mov     r13, r8
0x180006e1b  mov     ebx, [rbp+1F0h+arg_28]
0x180006e21  mov     r14, rdx
0x180006e24  mov     rsi, rcx
0x180006e27  cmp     qword ptr [rax+78h], 0
0x180006e2c  jz      loc_180007029
0x180006e32  test    rsi, rsi
0x180006e35  jnz     loc_180007044
0x180006e3b  mov     rsi, cs:hmodUser
0x180006e42  lea     rax, ?szUSER32@@3PAGA; "USER32"
0x180006e49  mov     [rsp+2F0h+SourceString], rax
0x180006e4e  bt      ebx, 0Dh
0x180006e52  jnb     short loc_180006E5C
0x180006e54  btr     ebx, 0Dh
0x180006e58  bts     ebx, 0Bh
0x180006e5c  cmp     rsi, cs:hmodUser
0x180006e63  jnz     short loc_180006E72
0x180006e65  test    r14, 0FFFFFFFFFFFF0000h
0x180006e6c  jz      loc_180006FEB
0x180006e72  mov     edi, ebx
0x180006e74  test    r12d, r12d
0x180006e77  jnz     loc_180007021
0x180006e7d  and     edi, 40h
0x180006e80  jz      loc_18000708B
0x180006e86  call    GetDpiForSystem
0x180006e8b  lea     ecx, [r12+5]
0x180006e90  mov     edx, eax
0x180006e92  cmp     r13, 3
0x180006e96  lea     eax, [rcx+2]
0x180006e99  cmovnz  ecx, eax
0x180006e9c  call    GetDpiDependentMetric
0x180006ea1  mov     r12d, eax
0x180006ea4  test    r15d, r15d
0x180006ea7  jnz     short loc_180006ECC
0x180006ea9  test    edi, edi
0x180006eab  jz      loc_1800070BA
0x180006eb1  call    GetDpiForSystem
0x180006eb6  xor     ecx, ecx
0x180006eb8  mov     edx, eax
0x180006eba  cmp     r13, 3
0x180006ebe  setnz   cl
0x180006ec1  add     ecx, 6
0x180006ec4  call    GetDpiDependentMetric
0x180006ec9  mov     r15d, eax
0x180006ecc  bt      ebx, 0Fh
0x180006ed0  jb      short loc_180006F35
0x180006ed2  mov     [rsp+2F0h+var_2C8], ebx; unsigned int
0x180006ed6  mov     r9d, r12d; nWidth
0x180006ed9  mov     r8, r13; unsigned __int16 *
0x180006edc  mov     [rsp+2F0h+var_2D0], r15d; unsigned int
0x180006ee1  mov     rdx, r14; unsigned __int16 *
0x180006ee4  mov     rcx, rsi; HINSTANCE
0x180006ee7  call    ?ObjectFromDIBResource@@YAPEAXPEAUHINSTANCE__@@PEBGPEAGKKI@Z; ObjectFromDIBResource(HINSTANCE__ *,ushort const *,ushort *,ulong,ulong,uint)
0x180006eec  mov     rdi, rax
0x180006eef  cmp     r13, 1
0x180006ef3  jnz     short loc_180006F0F
0x180006ef5  mov     [rsp+2F0h+var_2C8], ebx; unsigned int
0x180006ef9  mov     r9d, r12d; unsigned int
0x180006efc  mov     r8, r14; unsigned __int16 *
0x180006eff  mov     [rsp+2F0h+var_2D0], r15d; unsigned int
0x180006f04  mov     rdx, rsi; HINSTANCE
0x180006f07  mov     rcx, rax; HICON
0x180006f0a  call    ?CreateDpiCursors@@YAXPEAUHICON__@@PEAUHINSTANCE__@@PEBGKKK@Z; CreateDpiCursors(HICON__ *,HINSTANCE__ *,ushort const *,ulong,ulong,ulong)
0x180006f0f  mov     rax, rdi
0x180006f12  mov     rcx, [rbp+1F0h+var_50]
0x180006f19  xor     rcx, rsp; StackCookie
0x180006f1c  call    __security_check_cookie
0x180006f21  add     rsp, 2B8h
0x180006f28  pop     r15
0x180006f2a  pop     r14
0x180006f2c  pop     r13
0x180006f2e  pop     r12
0x180006f30  pop     rdi
0x180006f31  pop     rsi
0x180006f32  pop     rbx
0x180006f33  pop     rbp
0x180006f34  retn
0x180006f35  cmp     rsi, cs:hmodUser
0x180006f3c  mov     [rsp+2F0h+var_2B8], 0
0x180006f45  mov     [rsp+2F0h+var_2B0], r13d
0x180006f4a  mov     [rsp+2F0h+var_2A4], 0
0x180006f52  jnz     loc_180007093
0x180006f58  mov     [rsp+2F0h+var_2AC], 0
0x180006f61  mov     rdx, [rsp+2F0h+SourceString]; SourceString
0x180006f66  lea     rax, [rsp+2F0h+DestinationString]
0x180006f6b  xorps   xmm0, xmm0
0x180006f6e  mov     [rbp+1F0h+var_270], rax
0x180006f72  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x180006f77  mov     qword ptr [rsp+2F0h+DestinationString.Length], 0
0x180006f80  movups  xmmword ptr [rsp+2F0h+var_2A0.Length], xmm0
0x180006f85  mov     [rsp+2F0h+DestinationString.Buffer], 0
0x180006f8e  movups  [rsp+2F0h+var_290], xmm0
0x180006f93  mov     [rbp+1F0h+var_268], 0
0x180006f9b  call    cs:__imp_RtlInitUnicodeString
0x180006fa1  mov     dword ptr [rsp+2F0h+var_290+8], 0
0x180006fa9  lea     rdx, [rsp+2F0h+var_2A0]
0x180006fae  mov     qword ptr [rsp+2F0h+var_290], rdx
0x180006fb3  test    r14, 0FFFFFFFFFFFF0000h
0x180006fba  jnz     loc_1800070C2
0x180006fc0  xor     eax, eax
0x180006fc2  mov     [rsp+2F0h+var_2A0.Buffer], r14
0x180006fc7  mov     dword ptr [rsp+2F0h+var_2A0.Length], eax
0x180006fcb  mov     rcx, [rbp+1F0h+var_270]
0x180006fcf  lea     r8, [rsp+2F0h+var_2B8]
0x180006fd4  call    cs:__imp_NtUserFindExistingCursorIcon
0x180006fda  mov     rdi, rax
0x180006fdd  test    rax, rax
0x180006fe0  jnz     loc_180006F0F
0x180006fe6  jmp     loc_180006ED2
0x180006feb  xor     eax, eax
0x180006fed  lea     rdx, qword_1800A89B8
0x180006ff4  cmp     r13, 3
0x180006ff8  lea     rcx, qword_1800A89B0
0x180006fff  setnz   al
0x180007002  inc     eax
0x180007004  cmp     r13, 3
0x180007008  cmovnz  rcx, rdx
0x18000700c  sub     eax, 1
0x18000700f  js      loc_180006E72
0x180007015  cmp     [rcx], r14w
0x180007019  jz      short loc_180007066
0x18000701b  add     rcx, 6
0x18000701f  jmp     short loc_18000700C
0x180007021  and     edi, 40h
0x180007024  jmp     loc_180006EA4
0x180007029  mov     ecx, 0Eh
0x18000702e  call    cs:__imp_NtUserGetThreadState
0x180007034  test    rax, rax
0x180007037  jnz     loc_180006E32
0x18000703d  xor     eax, eax
0x18000703f  jmp     loc_180006F12
0x180007044  mov     edi, 104h
0x180007049  lea     rdx, [rbp+1F0h+Filename]; lpFilename
0x18000704d  mov     r8d, edi; nSize
0x180007050  mov     rcx, rsi; hModule
0x180007053  call    cs:__imp_GetModuleFileNameW
0x180007059  test    eax, eax
0x18000705b  jz      short loc_1800070A2
0x18000705d  lea     rax, [rbp+1F0h+Filename]
0x180007061  jmp     loc_180006E49
0x180007066  test    byte ptr [rcx+4], 1
0x18000706a  jz      short loc_180007081
0x18000706c  mov     rax, gs:30h
0x180007075  cmp     dword ptr [rax+810h], 400h
0x18000707f  jnb     short loc_18000703D
0x180007081  movzx   r14d, word ptr [rcx+2]
0x180007086  jmp     loc_180006E72
0x18000708b  xor     r12d, r12d
0x18000708e  jmp     loc_180006EA4
0x180007093  mov     dword ptr [rsp+2F0h+var_2AC], r12d
0x180007098  mov     dword ptr [rsp+2F0h+var_2AC+4], r15d
0x18000709d  jmp     loc_180006F61
0x1800070a2  mov     r9, rsi
0x1800070a5  lea     r8, qword_1800A8D38; unsigned __int16 *
0x1800070ac  mov     rdx, rdi; unsigned __int64
0x1800070af  lea     rcx, [rbp+1F0h+Filename]; unsigned __int16 *
0x1800070b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800070b8  jmp     short loc_18000705D
0x1800070ba  xor     r15d, r15d
0x1800070bd  jmp     loc_180006ECC
0x1800070c2  mov     rdx, r14; SourceString
0x1800070c5  lea     rcx, [rsp+2F0h+var_2A0]; DestinationString
0x1800070ca  call    cs:__imp_RtlInitUnicodeString
0x1800070d0  mov     rdx, qword ptr [rsp+2F0h+var_290]
0x1800070d5  jmp     loc_180006FCB
```
