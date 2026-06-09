# LogQuery(ushort const *,ulong,ulong)

- ea: `0x3839636a0`
- end: `0x383963817`
- name: `?LogQuery@@YAXPEBGKK@Z`
- size: `375`
- prototype: `void __fastcall(LPCVOID lpBuffer, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x38386a8a0`

## callees

- `0x3838434c0`
- `0x3839636a0`
- `0x383a9ec90`

## import_xrefs

- `MSVCR100!_wctime64` at `0x3839636df`
- `MSVCR100!_wctime64` at `0x3839636df`
- `MSVCR100!_time64` at `0x3839636d4`
- `MSVCR100!_time64` at `0x3839636d4`
- `KERNEL32!WriteFile` at `0x38396377a`
- `KERNEL32!WriteFile` at `0x38396379c`
- `KERNEL32!WriteFile` at `0x3839637ba`
- `KERNEL32!WriteFile` at `0x3839637dc`
- `KERNEL32!WriteFile` at `0x38396377a`
- `KERNEL32!WriteFile` at `0x38396379c`
- `KERNEL32!WriteFile` at `0x3839637ba`
- `KERNEL32!WriteFile` at `0x3839637dc`

## pseudocode

```c
void __fastcall LogQuery(LPCVOID lpBuffer, int a2, int a3)
{
  wchar_t *v6; // rax
  unsigned int FormattedMessage; // ebx
  int v8; // [rsp+28h] [rbp-4C0h]
  __int64 NumberOfBytesWritten; // [rsp+30h] [rbp-4B8h] BYREF
  __time64_t Time; // [rsp+38h] [rbp-4B0h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-4A8h] BYREF
  __int64 v12; // [rsp+60h] [rbp-488h]
  unsigned __int16 Buffer[552]; // [rsp+70h] [rbp-478h] BYREF

  LODWORD(NumberOfBytesWritten) = 0;
  _time64(&Time);
  v6 = _wctime64(&Time);
  v8 = a3;
  v11[0] = *(_QWORD *)v6;
  v11[1] = *((_QWORD *)v6 + 1);
  v11[2] = *((_QWORD *)v6 + 2);
  v11[3] = *((_QWORD *)v6 + 3);
  v12 = *((_QWORD *)v6 + 4);
  HIWORD(v12) = 0;
  FormattedMessage = LoadFormattedMessage(g_hinstance_language, 0x9C5Au, Buffer, 0x223u, v11, v8, NumberOfBytesWritten);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(g_csSQLPerf + 32LL) + 8LL))(g_csSQLPerf + 32LL);
  if ( g_fLogSlowQuery )
  {
    WriteFile(g_hPerfQueryFile, Buffer, 2 * FormattedMessage, (LPDWORD)&NumberOfBytesWritten, 0);
    WriteFile(g_hPerfQueryFile, L"\r\n", 4u, (LPDWORD)&NumberOfBytesWritten, 0);
    WriteFile(g_hPerfQueryFile, lpBuffer, 2 * a2, (LPDWORD)&NumberOfBytesWritten, 0);
    WriteFile(g_hPerfQueryFile, L"\r\n", 4u, (LPDWORD)&NumberOfBytesWritten, 0);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(g_csSQLPerf + 32LL) + 24LL))(g_csSQLPerf + 32LL);
}

```

## disassembly

```asm
0x3839636a0  mov     [rsp+arg_18], rbx
0x3839636a5  push    rbp
0x3839636a6  push    rsi
0x3839636a7  push    rdi
0x3839636a8  sub     rsp, 4D0h
0x3839636af  mov     rax, cs:__security_cookie
0x3839636b6  xor     rax, rsp
0x3839636b9  mov     [rsp+4E8h+var_28], rax
0x3839636c1  mov     rdi, rcx
0x3839636c4  lea     rcx, [rsp+4E8h+Time]; Time
0x3839636c9  xor     ebp, ebp
0x3839636cb  mov     ebx, r8d
0x3839636ce  mov     esi, edx
0x3839636d0  mov     dword ptr [rsp+4E8h+NumberOfBytesWritten], ebp
0x3839636d4  call    cs:__imp__time64
0x3839636da  lea     rcx, [rsp+4E8h+Time]; Time
0x3839636df  call    cs:__imp__wctime64
0x3839636e5  lea     r8, [rsp+4E8h+Buffer]; unsigned __int16 *
0x3839636ea  mov     r9d, 223h; unsigned int
0x3839636f0  mov     rcx, [rax]
0x3839636f3  mov     edx, 9C5Ah; unsigned int
0x3839636f8  mov     [rsp+4E8h+var_4C0], ebx
0x3839636fc  mov     [rsp+4E8h+var_4A8], rcx
0x383963701  mov     rcx, [rax+8]
0x383963705  mov     [rsp+4E8h+var_4A0], rcx
0x38396370a  mov     rcx, [rax+10h]
0x38396370e  mov     [rsp+4E8h+var_498], rcx
0x383963713  mov     rcx, [rax+18h]
0x383963717  mov     [rsp+4E8h+var_490], rcx
0x38396371c  mov     rax, [rax+20h]
0x383963720  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x383963727  mov     [rsp+4E8h+var_488], rax
0x38396372c  lea     rax, [rsp+4E8h+var_4A8]
0x383963731  mov     word ptr [rsp+4E8h+var_488+6], bp
0x383963736  mov     [rsp+4E8h+lpOverlapped], rax
0x38396373b  call    ?LoadFormattedMessage@@YAKPEAUHINSTANCE__@@KPEAGKZZ; LoadFormattedMessage(HINSTANCE__ *,ulong,ushort *,ulong,...)
0x383963740  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x383963747  mov     rdx, [rcx+20h]
0x38396374b  add     rcx, 20h ; ' '
0x38396374f  mov     ebx, eax
0x383963751  call    qword ptr [rdx+8]
0x383963754  cmp     cs:?g_fLogSlowQuery@@3HA, ebp; int g_fLogSlowQuery
0x38396375a  jz      loc_3839637E2
0x383963760  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x383963767  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x38396376b  lea     r9, [rsp+4E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x383963770  lea     rdx, [rsp+4E8h+Buffer]; lpBuffer
0x383963775  mov     [rsp+4E8h+lpOverlapped], rbp; lpOverlapped
0x38396377a  call    cs:__imp_WriteFile
0x383963780  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x383963787  lea     r9, [rsp+4E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x38396378c  lea     r8d, [rbp+4]; nNumberOfBytesToWrite
0x383963790  lea     rdx, asc_383915954; "\r\n"
0x383963797  mov     [rsp+4E8h+lpOverlapped], rbp; lpOverlapped
0x38396379c  call    cs:__imp_WriteFile
0x3839637a2  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x3839637a9  lea     r8d, [rsi+rsi]; nNumberOfBytesToWrite
0x3839637ad  lea     r9, [rsp+4E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x3839637b2  mov     rdx, rdi; lpBuffer
0x3839637b5  mov     [rsp+4E8h+lpOverlapped], rbp; lpOverlapped
0x3839637ba  call    cs:__imp_WriteFile
0x3839637c0  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x3839637c7  lea     r9, [rsp+4E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x3839637cc  lea     r8d, [rbp+4]; nNumberOfBytesToWrite
0x3839637d0  lea     rdx, asc_383915954; "\r\n"
0x3839637d7  mov     [rsp+4E8h+lpOverlapped], rbp; lpOverlapped
0x3839637dc  call    cs:__imp_WriteFile
0x3839637e2  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x3839637e9  mov     rax, [rcx+20h]
0x3839637ed  add     rcx, 20h ; ' '
0x3839637f1  call    qword ptr [rax+18h]
0x3839637f4  mov     rcx, [rsp+4E8h+var_28]
0x3839637fc  xor     rcx, rsp; StackCookie
0x3839637ff  call    __security_check_cookie
0x383963804  mov     rbx, [rsp+4E8h+arg_18]
0x38396380c  add     rsp, 4D0h
0x383963813  pop     rdi
0x383963814  pop     rsi
0x383963815  pop     rbp
0x383963816  retn
```
