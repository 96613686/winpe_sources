# IumpInvokeLimitedModeSecureService

- ea: `0x1400450a4`
- end: `0x14004531a`
- name: `IumpInvokeLimitedModeSecureService`
- size: `630`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, installer_update`

## callers

- `0x140014dd0`
- `0x140044be4`

## callees

- `0x1400119c4`
- `0x14002becc`
- `0x140045098`
- `0x1400450a4`
- `0x14007064c`
- `0x140074718`
- `0x140088748`
- `0x140089138`
- `0x14009a9a0`
- `0x14009cebc`
- `0x1400b8fbc`
- `0x1400b93e0`
- `0x1400b9dc8`
- `0x1400ba220`
- `0x1400bc0a8`

## pseudocode

```c
__int64 __fastcall IumpInvokeLimitedModeSecureService(__int64 a1, __int64 a2)
{
  ULONG_PTR v3; // rcx
  int v4; // esi
  int SecurePageList; // edi
  int started; // eax
  unsigned int v7; // ecx
  __int64 v8; // rdx
  __int64 result; // rax
  unsigned int v10; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+10h] BYREF

  v3 = *(unsigned __int16 *)(a1 + 2);
  v4 = a2;
  if ( (_DWORD)a2 && _InterlockedExchange(&IumpSingleThreadedServiceRequestEntered, 1) )
  {
    SecurePageList = -1073741790;
    goto LABEL_36;
  }
  if ( (unsigned __int16)v3 > 0x123u )
  {
    switch ( (_DWORD)v3 )
    {
      case 0x126:
        started = SkTerminate();
        goto LABEL_33;
      case 0x800:
        LOBYTE(v3) = *(_BYTE *)(a1 + 8);
        started = SkStartSecurePageIteration(
                    v3,
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 24),
                    *(_DWORD *)(a1 + 32),
                    *(_DWORD *)(a1 + 40));
        goto LABEL_33;
      case 0x801:
        LOBYTE(v3) = *(_BYTE *)(a1 + 8);
        v11 = 0;
        SecurePageList = SkEndSecurePageIteration(v3, &v11);
        if ( SecurePageList >= 0 )
          *(_QWORD *)(a1 + 16) = v11;
        goto LABEL_34;
      case 0x802:
        v8 = *(_QWORD *)(a1 + 16);
        LOBYTE(v3) = *(_BYTE *)(a1 + 8);
        LOBYTE(v11) = 0;
        v10 = 0;
        SecurePageList = SkGetSecurePageList(v3, v8, &v11, &v10);
        if ( SecurePageList >= 0 )
        {
          *(_QWORD *)(a1 + 16) = (unsigned __int8)v11;
          *(_QWORD *)(a1 + 24) = v10;
        }
        goto LABEL_34;
      case 0x803:
        SecurePageList = -1073741811;
        qword_14016B5E8 = 0;
        ShvlExitMinimalDispatchLoop();
        SkeResumeTimers(0);
        SkpSetHiberCrashState(1, &v11);
        IumpLimitedDispatchFromNormalDispatch = 0;
        goto LABEL_34;
    }
LABEL_37:
    SkeBugCheckEx(0x121u, 0xFFFFFFFFC000001CuLL, v3, 1u, 0);
  }
  if ( (_WORD)v3 == 291 )
  {
    started = SkpnppSwdValidateTrustlet();
    goto LABEL_33;
  }
  switch ( (_DWORD)v3 )
  {
    case 0x105:
      started = SkmmWriteProtectedPage(a1 + 8);
      goto LABEL_33;
    case 0x117:
      SkPrepareForCrashDump(0);
      goto LABEL_18;
    case 0x118:
      started = SkhalReportBugCheckProgress(
                  *(_DWORD *)(a1 + 8),
                  (int)a1 + 16,
                  *(_QWORD *)(a1 + 32),
                  *(_DWORD *)(a1 + 40),
                  *(_DWORD *)(a1 + 48));
      goto LABEL_33;
    case 0x11A:
LABEL_18:
      SecurePageList = 0;
      goto LABEL_34;
    case 0x11C:
      v7 = *(_DWORD *)(a1 + 32);
      if ( v7 > 0x40 )
      {
        SecurePageList = -2147483643;
        goto LABEL_34;
      }
      LOBYTE(a2) = *(_BYTE *)(a1 + 8);
      started = SkhalAccessPciDevice(
                  0,
                  a2,
                  *(unsigned int *)(a1 + 12),
                  *(unsigned int *)(a1 + 16),
                  *(_DWORD *)(a1 + 20),
                  *(_DWORD *)(a1 + 24),
                  *(_DWORD *)(a1 + 28),
                  v7,
                  a1 + 40);
      goto LABEL_33;
  }
  if ( (_DWORD)v3 != 290 )
    goto LABEL_37;
  started = SkmmNtKernelShadowStackAssist(
              *(_DWORD *)(a1 + 8),
              *(_QWORD *)(a1 + 16),
              *(_QWORD *)(a1 + 24),
              *(_QWORD *)(a1 + 32),
              *(_QWORD *)(a1 + 40),
              *(_DWORD *)(a1 + 48));
LABEL_33:
  SecurePageList = started;
LABEL_34:
  if ( v4 )
    _InterlockedExchange(&IumpSingleThreadedServiceRequestEntered, 0);
LABEL_36:
  *(_WORD *)(a1 + 2) = 0;
  result = SecurePageList;
  *(_QWORD *)(a1 + 8) = SecurePageList;
  *(_BYTE *)(a1 + 1) = 1;
  return result;
}

```

## disassembly

```asm
0x1400450a4  mov     [rsp+arg_10], rbx
0x1400450a9  mov     [rsp+arg_18], rsi
0x1400450ae  push    rdi
0x1400450af  sub     rsp, 50h
0x1400450b3  mov     rbx, rcx
0x1400450b6  movzx   ecx, word ptr [rcx+2]
0x1400450ba  mov     esi, edx
0x1400450bc  test    edx, edx
0x1400450be  jz      short loc_1400450D9
0x1400450c0  mov     eax, 1
0x1400450c5  xchg    eax, cs:IumpSingleThreadedServiceRequestEntered
0x1400450cb  test    eax, eax
0x1400450cd  jz      short loc_1400450D9
0x1400450cf  mov     edi, 0C0000022h
0x1400450d4  jmp     loc_1400452D4
0x1400450d9  mov     eax, 123h
0x1400450de  cmp     cx, ax
0x1400450e1  ja      loc_1400451DD
0x1400450e7  jz      loc_1400451D3
0x1400450ed  mov     eax, ecx
0x1400450ef  sub     eax, 105h
0x1400450f4  jz      loc_1400451C5
0x1400450fa  sub     eax, 12h
0x1400450fd  jz      loc_1400451B7
0x140045103  sub     eax, 1
0x140045106  jz      loc_140045197
0x14004510c  sub     eax, 2
0x14004510f  jz      loc_1400451BE
0x140045115  sub     eax, 2
0x140045118  jz      short loc_14004514C
0x14004511a  cmp     eax, 6
0x14004511d  jnz     loc_1400452F6
0x140045123  mov     eax, [rbx+30h]
0x140045126  mov     r9, [rbx+20h]
0x14004512a  mov     r8, [rbx+18h]
0x14004512e  mov     rdx, [rbx+10h]
0x140045132  mov     ecx, [rbx+8]
0x140045135  mov     [rsp+58h+var_30], eax
0x140045139  mov     rax, [rbx+28h]
0x14004513d  mov     [rsp+58h+BugCheckParameter4], rax
0x140045142  call    SkmmNtKernelShadowStackAssist
0x140045147  jmp     loc_1400452C6
0x14004514c  mov     ecx, [rbx+20h]
0x14004514f  cmp     ecx, 40h ; '@'
0x140045152  jbe     short loc_14004515E
0x140045154  mov     edi, 80000005h
0x140045159  jmp     loc_1400452C8
0x14004515e  mov     r9d, [rbx+10h]
0x140045162  lea     rax, [rbx+28h]
0x140045166  mov     r8d, [rbx+0Ch]
0x14004516a  mov     dl, [rbx+8]
0x14004516d  mov     [rsp+58h+var_18], rax
0x140045172  mov     eax, [rbx+1Ch]
0x140045175  mov     [rsp+58h+var_20], ecx
0x140045179  xor     ecx, ecx
0x14004517b  mov     [rsp+58h+var_28], eax
0x14004517f  mov     eax, [rbx+18h]
0x140045182  mov     [rsp+58h+var_30], eax
0x140045186  mov     eax, [rbx+14h]
0x140045189  mov     dword ptr [rsp+58h+BugCheckParameter4], eax
0x14004518d  call    SkhalAccessPciDevice
0x140045192  jmp     loc_1400452C6
0x140045197  mov     eax, [rbx+30h]
0x14004519a  lea     rdx, [rbx+10h]
0x14004519e  mov     r9d, [rbx+28h]
0x1400451a2  mov     r8, [rbx+20h]
0x1400451a6  mov     ecx, [rbx+8]
0x1400451a9  mov     dword ptr [rsp+58h+BugCheckParameter4], eax
0x1400451ad  call    SkhalReportBugCheckProgress
0x1400451b2  jmp     loc_1400452C6
0x1400451b7  xor     ecx, ecx
0x1400451b9  call    SkPrepareForCrashDump
0x1400451be  xor     edi, edi
0x1400451c0  jmp     loc_1400452C8
0x1400451c5  lea     rcx, [rbx+8]
0x1400451c9  call    SkmmWriteProtectedPage
0x1400451ce  jmp     loc_1400452C6
0x1400451d3  call    SkpnppSwdValidateTrustlet
0x1400451d8  jmp     loc_1400452C6
0x1400451dd  mov     eax, ecx
0x1400451df  sub     eax, 126h
0x1400451e4  jz      loc_1400452C1
0x1400451ea  sub     eax, 6DAh
0x1400451ef  jz      loc_1400452A4
0x1400451f5  sub     eax, 1
0x1400451f8  jz      loc_14004527F
0x1400451fe  sub     eax, 1
0x140045201  jz      short loc_140045243
0x140045203  cmp     eax, 1
0x140045206  jnz     loc_1400452F6
0x14004520c  mov     edi, 0C000000Dh
0x140045211  mov     cs:qword_14016B5E8, 0
0x14004521c  call    ShvlExitMinimalDispatchLoop
0x140045221  xor     ecx, ecx
0x140045223  call    SkeResumeTimers
0x140045228  lea     rdx, [rsp+58h+arg_8]
0x14004522d  mov     ecx, 1
0x140045232  call    SkpSetHiberCrashState
0x140045237  mov     cs:IumpLimitedDispatchFromNormalDispatch, 0
0x14004523e  jmp     loc_1400452C8
0x140045243  mov     rdx, [rbx+10h]
0x140045247  lea     r9, [rsp+58h+arg_0]
0x14004524c  mov     cl, [rbx+8]
0x14004524f  lea     r8, [rsp+58h+arg_8]
0x140045254  mov     byte ptr [rsp+58h+arg_8], 0
0x140045259  mov     [rsp+58h+arg_0], 0
0x140045261  call    SkGetSecurePageList
0x140045266  mov     edi, eax
0x140045268  test    eax, eax
0x14004526a  js      short loc_1400452C8
0x14004526c  movzx   eax, byte ptr [rsp+58h+arg_8]
0x140045271  mov     [rbx+10h], rax
0x140045275  mov     eax, [rsp+58h+arg_0]
0x140045279  mov     [rbx+18h], rax
0x14004527d  jmp     short loc_1400452C8
0x14004527f  mov     cl, [rbx+8]
0x140045282  lea     rdx, [rsp+58h+arg_8]
0x140045287  mov     [rsp+58h+arg_8], 0
0x14004528f  call    SkEndSecurePageIteration
0x140045294  mov     edi, eax
0x140045296  test    eax, eax
0x140045298  js      short loc_1400452C8
0x14004529a  mov     eax, [rsp+58h+arg_8]
0x14004529e  mov     [rbx+10h], rax
0x1400452a2  jmp     short loc_1400452C8
0x1400452a4  mov     eax, [rbx+28h]
0x1400452a7  mov     r9d, [rbx+20h]
0x1400452ab  mov     r8, [rbx+18h]
0x1400452af  mov     rdx, [rbx+10h]
0x1400452b3  mov     cl, [rbx+8]
0x1400452b6  mov     dword ptr [rsp+58h+BugCheckParameter4], eax
0x1400452ba  call    SkStartSecurePageIteration
0x1400452bf  jmp     short loc_1400452C6
0x1400452c1  call    SkTerminate
0x1400452c6  mov     edi, eax
0x1400452c8  test    esi, esi
0x1400452ca  jz      short loc_1400452D4
0x1400452cc  xor     eax, eax
0x1400452ce  xchg    eax, cs:IumpSingleThreadedServiceRequestEntered
0x1400452d4  mov     rsi, [rsp+58h+arg_18]
0x1400452d9  xor     eax, eax
0x1400452db  mov     [rbx+2], ax
0x1400452df  movsxd  rax, edi
0x1400452e2  mov     [rbx+8], rax
0x1400452e6  mov     byte ptr [rbx+1], 1
0x1400452ea  mov     rbx, [rsp+58h+arg_10]
0x1400452ef  add     rsp, 50h
0x1400452f3  pop     rdi
0x1400452f4  retn
0x1400452f6  mov     r8, rcx; BugCheckParameter2
0x1400452f9  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x140045302  mov     ecx, 121h; BugCheckCode
0x140045307  mov     rdx, 0FFFFFFFFC000001Ch; BugCheckParameter1
0x14004530e  mov     r9d, 1; BugCheckParameter3
0x140045314  call    SkeBugCheckEx
```
