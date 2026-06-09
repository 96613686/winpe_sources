# SetThreadDpiAwarenessContext

- ea: `0x180010e60`
- end: `0x18001104f`
- name: `SetThreadDpiAwarenessContext`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180026f90`
- `0x180030f00`

## callees

- `0x180010e60`
- `0x180011604`
- `0x180069f18`

## import_xrefs

- `win32u!NtUserTraceLoggingSendMixedModeTelemetry` at `0x180010f0e`
- `win32u!NtUserTraceLoggingSendMixedModeTelemetry` at `0x180010f0e`
- `win32u!NtUserGetThreadState` at `0x180010f7a`
- `win32u!NtUserGetThreadState` at `0x180010f7a`
- `ntdll!RtlSetLastWin32Error` at `0x180010ffc`
- `ntdll!RtlSetLastWin32Error` at `0x180011044`
- `ntdll!RtlSetLastWin32Error` at `0x180010ffc`
- `ntdll!RtlSetLastWin32Error` at `0x180011044`

## pseudocode

```c
__int64 __fastcall SetThreadDpiAwarenessContext(__int64 a1)
{
  unsigned int v2; // ebx
  struct _TEB *v3; // rsi
  __int64 v4; // rcx
  struct _TEB *v5; // rax
  int v6; // edx
  __int64 result; // rax
  int v8; // ebp
  unsigned int v9; // ecx

  if ( !NtCurrentTeb()->Win32ThreadInfo )
  {
    result = NtUserGetThreadState(14);
    if ( !result )
      return result;
  }
  v2 = 0;
  v3 = NtCurrentTeb();
  if ( !a1 )
    goto LABEL_15;
  v4 = HIDWORD(v3->Win32ClientInfo[33]);
  if ( a1 != v4 )
  {
    switch ( a1 )
    {
      case -1LL:
        LODWORD(v4) = 24592;
        goto LABEL_4;
      case -2LL:
        LODWORD(v4) = ((GetDpiForCurrentProcess() & 0x1FF) << 8) | 0x11;
        goto LABEL_4;
      case -3LL:
        v8 = 18;
LABEL_27:
        LODWORD(v4) = v8;
        goto LABEL_4;
    }
LABEL_15:
    if ( a1 == -4 )
    {
      LODWORD(v4) = 34;
      goto LABEL_4;
    }
    if ( a1 == -5 )
    {
      LODWORD(v4) = 1073766416;
      goto LABEL_4;
    }
    v8 = 0;
    v9 = a1 & 0x7FFFFFFF;
    if ( (a1 & 0x7FFFFFFF) != 0x22
      && v9 != 24592
      && v9 != 18
      && v9 != 1073766416
      && ((a1 & 0x7FFE00FF) != 0x11 || !(unsigned __int8)IsDpiValidPlateau((v9 >> 8) & 0x1FF)) )
    {
      RtlSetLastWin32Error(0x57u);
      LODWORD(v4) = 0;
      goto LABEL_4;
    }
    if ( (a1 & 0xF) == 1 && (((unsigned int)a1 >> 8) & 0x1FF) != (unsigned __int16)GetDpiForCurrentProcess() )
      RtlSetLastWin32Error(0x57u);
    else
      v8 = a1;
    goto LABEL_27;
  }
LABEL_4:
  if ( (_DWORD)v4 )
  {
    v5 = NtCurrentTeb();
    v6 = 0;
    if ( (int)v4 >= 0 )
      v6 = v4;
    v2 = v5->Win32ClientInfo[29];
    if ( v2 != v6 )
    {
      HIDWORD(v5->Win32ClientInfo[29]) = 1;
      LODWORD(v5->Win32ClientInfo[29]) = v6;
    }
    if ( !v2 )
      v2 = gDefaultDpiContext | 0x80000000;
    HIDWORD(v3->Win32ClientInfo[33]) = v2;
  }
  if ( !gfSentMixedModeTelemetry )
  {
    NtUserTraceLoggingSendMixedModeTelemetry();
    gfSentMixedModeTelemetry = 1;
  }
  return v2;
}

```

## disassembly

```asm
0x180010e60  push    rdi
0x180010e62  sub     rsp, 20h
0x180010e66  mov     rax, gs:30h
0x180010e6f  mov     rdi, rcx
0x180010e72  cmp     qword ptr [rax+78h], 0
0x180010e77  jz      loc_180010F75
0x180010e7d  mov     [rsp+28h+arg_0], rbx
0x180010e82  xor     ebx, ebx
0x180010e84  mov     [rsp+28h+arg_8], rbp
0x180010e89  mov     [rsp+28h+arg_10], rsi
0x180010e8e  mov     rsi, gs:30h
0x180010e97  mov     [rsp+28h+arg_18], r14
0x180010e9c  test    rdi, rdi
0x180010e9f  jz      loc_180010F2B
0x180010ea5  mov     ecx, [rsi+90Ch]
0x180010eab  cmp     rdi, rcx
0x180010eae  jnz     loc_180010F8F
0x180010eb4  mov     r14, [rsp+28h+arg_18]
0x180010eb9  mov     rbp, [rsp+28h+arg_8]
0x180010ebe  test    ecx, ecx
0x180010ec0  jz      short loc_180010F00
0x180010ec2  mov     rax, gs:30h
0x180010ecb  xor     edx, edx
0x180010ecd  test    ecx, ecx
0x180010ecf  cmovns  edx, ecx
0x180010ed2  mov     ebx, [rax+8E8h]
0x180010ed8  cmp     ebx, edx
0x180010eda  jz      short loc_180010EEC
0x180010edc  mov     dword ptr [rax+8ECh], 1
0x180010ee6  mov     [rax+8E8h], edx
0x180010eec  test    ebx, ebx
0x180010eee  jnz     short loc_180010EFA
0x180010ef0  mov     ebx, cs:gDefaultDpiContext
0x180010ef6  bts     ebx, 1Fh
0x180010efa  mov     [rsi+90Ch], ebx
0x180010f00  cmp     cs:?gfSentMixedModeTelemetry@@3HA, 0; int gfSentMixedModeTelemetry
0x180010f07  mov     rsi, [rsp+28h+arg_10]
0x180010f0c  jnz     short loc_180010F1E
0x180010f0e  call    cs:__imp_NtUserTraceLoggingSendMixedModeTelemetry
0x180010f14  mov     cs:?gfSentMixedModeTelemetry@@3HA, 1; int gfSentMixedModeTelemetry
0x180010f1e  mov     eax, ebx
0x180010f20  mov     rbx, [rsp+28h+arg_0]
0x180010f25  add     rsp, 20h
0x180010f29  pop     rdi
0x180010f2a  retn
0x180010f2b  cmp     rdi, 0FFFFFFFFFFFFFFFCh
0x180010f2f  jz      loc_180011033
0x180010f35  cmp     rdi, 0FFFFFFFFFFFFFFFBh
0x180010f39  jz      loc_180011009
0x180010f3f  mov     ecx, edi
0x180010f41  xor     ebp, ebp
0x180010f43  btr     ecx, 1Fh
0x180010f47  cmp     ecx, 22h ; '"'
0x180010f4a  jnz     short loc_180010FB9
0x180010f4c  mov     r14d, 1FFh
0x180010f52  mov     eax, edi
0x180010f54  and     al, 0Fh
0x180010f56  cmp     al, 1
0x180010f58  jnz     short loc_180010F71
0x180010f5a  call    GetDpiForCurrentProcess
0x180010f5f  mov     ecx, edi
0x180010f61  shr     ecx, 8
0x180010f64  and     cx, r14w
0x180010f68  cmp     cx, ax
0x180010f6b  jnz     loc_18001103F
0x180010f71  mov     ebp, edi
0x180010f73  jmp     short loc_180010FA6
0x180010f75  mov     ecx, 0Eh
0x180010f7a  call    cs:__imp_NtUserGetThreadState
0x180010f80  test    rax, rax
0x180010f83  jnz     loc_180010E7D
0x180010f89  add     rsp, 20h
0x180010f8d  pop     rdi
0x180010f8e  retn
0x180010f8f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180010f93  jz      short loc_180010FAD
0x180010f95  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180010f99  jz      short loc_180011015
0x180010f9b  cmp     rdi, 0FFFFFFFFFFFFFFFDh
0x180010f9f  jnz     short loc_180010F2B
0x180010fa1  mov     ebp, 12h
0x180010fa6  mov     ecx, ebp
0x180010fa8  jmp     loc_180010EB4
0x180010fad  mov     ebp, 6010h
0x180010fb2  mov     ecx, ebp
0x180010fb4  jmp     loc_180010EB4
0x180010fb9  cmp     ecx, 6010h
0x180010fbf  jz      short loc_180010F4C
0x180010fc1  cmp     ecx, 12h
0x180010fc4  jz      short loc_180010F4C
0x180010fc6  cmp     ecx, 40006010h
0x180010fcc  jz      loc_180010F4C
0x180010fd2  mov     eax, ecx
0x180010fd4  and     eax, 0FFFE00FFh
0x180010fd9  cmp     eax, 11h
0x180010fdc  jnz     short loc_180010FF7
0x180010fde  shr     ecx, 8
0x180010fe1  mov     r14d, 1FFh
0x180010fe7  and     ecx, r14d
0x180010fea  call    IsDpiValidPlateau
0x180010fef  test    al, al
0x180010ff1  jnz     loc_180010F52
0x180010ff7  mov     ecx, 57h ; 'W'; LastError
0x180010ffc  call    cs:__imp_RtlSetLastWin32Error
0x180011002  mov     ecx, ebp
0x180011004  jmp     loc_180010EB4
0x180011009  mov     ebp, 40006010h
0x18001100e  mov     ecx, ebp
0x180011010  jmp     loc_180010EB4
0x180011015  call    GetDpiForCurrentProcess
0x18001101a  movzx   ebp, ax
0x18001101d  mov     r14d, 1FFh
0x180011023  and     ebp, r14d
0x180011026  shl     ebp, 8
0x180011029  or      ebp, 11h
0x18001102c  mov     ecx, ebp
0x18001102e  jmp     loc_180010EB4
0x180011033  mov     ebp, 22h ; '"'
0x180011038  mov     ecx, ebp
0x18001103a  jmp     loc_180010EB4
0x18001103f  mov     ecx, 57h ; 'W'; LastError
0x180011044  call    cs:__imp_RtlSetLastWin32Error
0x18001104a  jmp     loc_180010FA6
```
