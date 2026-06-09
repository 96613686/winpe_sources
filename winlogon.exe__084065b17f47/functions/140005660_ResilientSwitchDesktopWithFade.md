# ResilientSwitchDesktopWithFade

- ea: `0x140005660`
- end: `0x1400057ec`
- name: `ResilientSwitchDesktopWithFade`
- size: `396`
- prototype: `__int64 __fastcall(HDESK hDesktop)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400957a4`

## callees

- `0x140005660`
- `0x1400057f4`
- `0x14004df08`
- `0x14004ea3c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400056f9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400056f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056d3`
- `ntdll!NtSetInformationThread` at `0x1400056a9`
- `ntdll!NtSetInformationThread` at `0x140005740`
- `ntdll!NtSetInformationThread` at `0x1400056a9`
- `ntdll!NtSetInformationThread` at `0x140005740`
- `ext-ms-win-ntuser-private-l1-1-0!SwitchDesktopWithFade` at `0x140005794`
- `ext-ms-win-ntuser-private-l1-1-0!SwitchDesktopWithFade` at `0x140005794`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SwitchDesktop` at `0x1400056c9`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SwitchDesktop` at `0x1400056c9`

## pseudocode

```c
__int64 __fastcall ResilientSwitchDesktopWithFade(HDESK hDesktop, int a2, unsigned int a3, unsigned int a4)
{
  unsigned int v7; // esi
  NTSTATUS v9; // r14d
  DWORD LastError; // eax
  DWORD v12; // ebx
  unsigned int v13; // edi
  int ThreadInformation; // [rsp+70h] [rbp+18h] BYREF

  v7 = 0;
  ThreadInformation = 1;
  v9 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadLastSystemCall|0x20, &ThreadInformation, 4u);
  while ( !(a3 ? SwitchDesktopWithFade(hDesktop, a3, a4) : SwitchDesktop(hDesktop)) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, LastError, a3);
    }
    if ( v7 >= 0xA )
    {
      if ( !a2 )
        goto LABEL_10;
    }
    else
    {
      ++v7;
    }
    Sleep(100 * v7);
  }
  v12 = 0;
LABEL_10:
  if ( !v9 )
  {
    ThreadInformation = 0;
    v13 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadLastSystemCall|0x20, &ThreadInformation, 4u);
    if ( v13 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, v13);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140005660  mov     rax, rsp
0x140005663  push    rdi
0x140005664  push    r13
0x140005666  sub     rsp, 48h
0x14000566a  mov     [rax+10h], rbp
0x14000566e  mov     edi, r8d
0x140005671  mov     [rax+20h], rsi
0x140005675  lea     r8, [rax+18h]; ThreadInformation
0x140005679  mov     [rax-18h], r12
0x14000567d  mov     rbp, rcx
0x140005680  mov     [rax-20h], r14
0x140005684  mov     r12d, edx
0x140005687  mov     [rax-28h], r15
0x14000568b  xor     esi, esi
0x14000568d  mov     r15d, r9d
0x140005690  mov     dword ptr [rax+18h], 1
0x140005697  mov     r9d, 4; ThreadInformationLength
0x14000569d  mov     edx, 35h ; '5'; ThreadInformationClass
0x1400056a2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400056a9  call    cs:__imp_NtSetInformationThread
0x1400056af  lea     r13, WPP_GLOBAL_Control
0x1400056b6  mov     [rsp+58h+arg_0], rbx
0x1400056bb  mov     r14d, eax
0x1400056be  mov     rcx, rbp; hDesktop
0x1400056c1  test    edi, edi
0x1400056c3  jnz     loc_14000578F
0x1400056c9  call    cs:__imp_SwitchDesktop
0x1400056cf  test    eax, eax
0x1400056d1  jnz     short loc_140005701
0x1400056d3  call    cs:__imp_GetLastError
0x1400056d9  mov     ebx, eax
0x1400056db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400056e2  cmp     rcx, r13
0x1400056e5  jnz     loc_14000579F
0x1400056eb  cmp     esi, 0Ah
0x1400056ee  jnb     loc_1400057D4
0x1400056f4  inc     esi
0x1400056f6  imul    ecx, esi, 64h ; 'd'; dwMilliseconds
0x1400056f9  call    cs:__imp_Sleep
0x1400056ff  jmp     short loc_1400056BE
0x140005701  xor     ebx, ebx
0x140005703  mov     r15, [rsp+58h+var_28]
0x140005708  test    r14d, r14d
0x14000570b  mov     r14, [rsp+58h+var_20]
0x140005710  mov     r12, [rsp+58h+var_18]
0x140005715  mov     rsi, [rsp+58h+arg_18]
0x14000571a  mov     rbp, [rsp+58h+arg_8]
0x14000571f  jnz     short loc_140005780
0x140005721  mov     r9d, 4; ThreadInformationLength
0x140005727  mov     [rsp+58h+ThreadInformation], 0
0x14000572f  lea     r8, [rsp+58h+ThreadInformation]; ThreadInformation
0x140005734  mov     edx, 35h ; '5'; ThreadInformationClass
0x140005739  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140005740  call    cs:__imp_NtSetInformationThread
0x140005746  mov     edi, eax
0x140005748  test    eax, eax
0x14000574a  jnz     loc_1400057E2
0x140005750  mov     rcx, cs:WPP_GLOBAL_Control
0x140005757  cmp     rcx, r13
0x14000575a  jz      short loc_140005780
0x14000575c  test    byte ptr [rcx+1Ch], 4
0x140005760  jz      short loc_140005780
0x140005762  cmp     byte ptr [rcx+19h], 2
0x140005766  jb      short loc_140005780
0x140005768  mov     rcx, [rcx+10h]
0x14000576c  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x140005773  mov     edx, 0Ch
0x140005778  mov     r9d, edi
0x14000577b  call    WPP_SF_d
0x140005780  mov     eax, ebx
0x140005782  mov     rbx, [rsp+58h+arg_0]
0x140005787  add     rsp, 48h
0x14000578b  pop     r13
0x14000578d  pop     rdi
0x14000578e  retn
0x14000578f  mov     r8d, r15d
0x140005792  mov     edx, edi
0x140005794  call    cs:__imp_SwitchDesktopWithFade
0x14000579a  jmp     loc_1400056CF
0x14000579f  test    byte ptr [rcx+1Ch], 4
0x1400057a3  jz      loc_1400056EB
0x1400057a9  cmp     byte ptr [rcx+19h], 2
0x1400057ad  jb      loc_1400056EB
0x1400057b3  mov     rcx, [rcx+10h]
0x1400057b7  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x1400057be  mov     edx, 0Bh
0x1400057c3  mov     [rsp+58h+var_38], edi
0x1400057c7  mov     r9d, eax
0x1400057ca  call    WPP_SF_DD
0x1400057cf  jmp     loc_1400056EB
0x1400057d4  test    r12d, r12d
0x1400057d7  jz      loc_140005703
0x1400057dd  jmp     loc_1400056F6
0x1400057e2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "statusUndo == STATUS_SUCCESS")
0x1400057e7  jmp     loc_140005750
```
