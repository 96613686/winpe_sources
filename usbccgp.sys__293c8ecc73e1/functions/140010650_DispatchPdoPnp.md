# DispatchPdoPnp

- ea: `0x140010650`
- end: `0x140010af7`
- name: `DispatchPdoPnp`
- size: `1191`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140028630`

## callees

- `0x140003388`
- `0x140006d40`
- `0x1400090e0`
- `0x14000a6cc`
- `0x14000d444`
- `0x14000d900`
- `0x14000e608`
- `0x14000e660`
- `0x140010650`
- `0x140012474`
- `0x14001257c`
- `0x140014060`
- `0x1400242a4`
- `0x1400249d4`
- `0x1400253c4`
- `0x1400259e4`
- `0x14002ad60`
- `0x14002b6cc`
- `0x14002befc`
- `0x14002ced0`
- `0x14002d07c`
- `0x14002e06c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010729`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400109af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010729`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400109af`
- `ntoskrnl!KeReleaseMutex` at `0x140010814`
- `ntoskrnl!KeReleaseMutex` at `0x140010814`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001075d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400109e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001075d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400109e3`
- `ntoskrnl!ExAllocatePool2` at `0x140010a14`
- `ntoskrnl!ExAllocatePool2` at `0x140010a14`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140010744`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140010777`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x1400109ca`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140010744`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x140010777`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x1400109ca`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x140010978`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x140010978`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterPdoWithParentPdo` at `0x14001091f`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterPdoWithParentPdo` at `0x14001091f`

## pseudocode

```c
__int64 __fastcall DispatchPdoPnp(_QWORD *PeekContext, __int64 a2, int a3)
{
  __int64 v4; // r15
  unsigned int v6; // edx
  int v8; // esi
  int DeviceText; // eax
  KIRQL v10; // r14
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rcx
  _QWORD *v14; // r14
  int v15; // edx
  KIRQL v16; // r12
  __int64 Pool2; // rax
  char v19; // [rsp+70h] [rbp+8h] BYREF

  v4 = PeekContext[29];
  v6 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL);
  if ( v6 > 9 )
  {
    switch ( v6 )
    {
      case 0xBu:
        InstallExtPropDesc(PeekContext);
        QuerySelectiveSuspendRegistryFlag(PeekContext);
        QueryAllowIdleIrpInD3RegistryFlag(PeekContext);
        QueryEndpointPriorities(PeekContext);
        break;
      case 0xCu:
        DeviceText = GetDeviceText(PeekContext, a2);
        goto LABEL_14;
      case 0x13u:
        DeviceText = QueryFunctionPdoID(PeekContext, a2);
        goto LABEL_14;
      case 0x14u:
        if ( *(_BYTE *)(v4 + 1376) == 1 && *((_BYTE *)PeekContext + 407) == 1 || *((_DWORD *)PeekContext + 5) == 3 )
        {
          *(_QWORD *)(a2 + 56) |= 4uLL;
        }
        else if ( *((_DWORD *)PeekContext + 5) == 6 )
        {
          *(_QWORD *)(a2 + 56) |= 1uLL;
        }
        else if ( (unsigned int)(*((_DWORD *)PeekContext + 5) - 7) <= 1 )
        {
          *(_QWORD *)(a2 + 56) |= 8uLL;
        }
        break;
      default:
        switch ( v6 )
        {
          case 0x15u:
            Pool2 = ExAllocatePool2(256, 24, 1130525525);
            if ( Pool2 )
            {
              *(_QWORD *)(Pool2 + 16) = 15;
              v8 = 0;
              *(GUID *)Pool2 = GUID_BUS_TYPE_USB;
            }
            else
            {
              v8 = -1073741670;
              Pool2 = 0;
            }
            *(_QWORD *)(a2 + 56) = Pool2;
            break;
          case 0x16u:
            return (unsigned int)HandlePdoDeviceUsageNotification(PeekContext, a2);
          case 0x17u:
            v8 = 0;
            *((_DWORD *)PeekContext + 6) = *((_DWORD *)PeekContext + 5);
            *((_DWORD *)PeekContext + 5) = 9;
            if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
            {
              v16 = KeAcquireSpinLockRaiseToDpc(PeekContext + 52);
              if ( PeekContext[53] )
              {
                SleepstudyHelper_UnregisterComponent();
                PeekContext[53] = 0;
              }
              KeReleaseSpinLock(PeekContext + 52, v16);
            }
            break;
          case 0x19u:
            v8 = 0;
            if ( g_SleepstudyLibraryHandle )
            {
              v14 = PeekContext + 53;
              if ( !PeekContext[53] )
              {
                v8 = SleepstudyHelper_RegisterPdoWithParentPdo(
                       g_SleepstudyLibraryHandle,
                       *(_QWORD *)(v4 + 24),
                       PeekContext[28],
                       PeekContext + 53);
                if ( v8 >= 0 )
                {
                  SleepstudyHelper_ComponentActive(*v14);
                }
                else
                {
                  *v14 = 0;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v15) = 3;
                    WPP_RECORDER_SF_d(
                      PeekContext[49],
                      v15,
                      8,
                      37,
                      (__int64)WPP_54beca300c4a353e079921b0991edb26_Traceguids,
                      v8);
                  }
                }
              }
            }
            break;
          default:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              LOBYTE(v6) = 5;
              WPP_RECORDER_SF_qc(PeekContext[49], v6, a3, 38);
            }
            v8 = *(_DWORD *)(a2 + 48);
            break;
        }
LABEL_73:
        UsbcCompleteIrp(v4, (unsigned int)v8, a2);
        return (unsigned int)v8;
    }
    goto LABEL_72;
  }
  switch ( v6 )
  {
    case 9u:
      DeviceText = QueryFunctionCapabilities(PeekContext, a2);
      goto LABEL_14;
    case 0u:
      ResetPdoExtension(v4, PeekContext);
      LOBYTE(v11) = 1;
      CancelFdoIdleIrp(v4, v11);
      v12 = *((_DWORD *)PeekContext + 5);
      *((_DWORD *)PeekContext + 6) = v12;
      *((_DWORD *)PeekContext + 5) = 2;
      if ( !v12 )
      {
        v13 = PeekContext[28];
        v19 = 0;
        if ( (int)GetD3Policy(v13, &v19) >= 0 && v19 == 1 )
        {
          AcquireMutex((PVOID)(v4 + 520));
          *((_BYTE *)PeekContext + 117) = 1;
          if ( *(_BYTE *)(v4 + 441) )
            ChangeParentD3ColdStateLocked(v4);
          KeReleaseMutex((PRKMUTEX)(v4 + 520), 0);
        }
      }
      if ( *(_BYTE *)(v4 + 1362) && *(_BYTE *)(PeekContext[48] + 59LL) )
        LockSyncSendSetFeatureControlRequestForFunctionSuspend(v4, PeekContext, 2);
      goto LABEL_72;
    case 1u:
      goto LABEL_72;
    case 2u:
      if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
      {
        v10 = KeAcquireSpinLockRaiseToDpc(PeekContext + 52);
        if ( PeekContext[53] )
        {
          SleepstudyHelper_UnregisterComponent();
          PeekContext[53] = 0;
        }
        KeReleaseSpinLock(PeekContext + 52, v10);
      }
      else if ( PeekContext[53] )
      {
        SleepstudyHelper_UnregisterComponent();
        PeekContext[53] = 0;
      }
      DeviceText = PdoRemoveDevice(PeekContext);
      goto LABEL_14;
    case 3u:
      goto LABEL_72;
    case 4u:
      if ( *((_DWORD *)PeekContext + 5) == 2 )
      {
        *((_DWORD *)PeekContext + 6) = 2;
        *((_DWORD *)PeekContext + 5) = 6;
      }
      goto LABEL_72;
    case 5u:
    case 6u:
LABEL_72:
      v8 = 0;
      goto LABEL_73;
    case 7u:
      DeviceText = QueryFunctionDeviceRelations(PeekContext, a2);
LABEL_14:
      v8 = DeviceText;
      goto LABEL_73;
  }
  return (unsigned int)HandlePdoQueryInterface(PeekContext, a2);
}

```

## disassembly

```asm
0x140010650  mov     [rsp+arg_8], rbx
0x140010655  mov     [rsp+arg_10], rbp
0x14001065a  push    rsi
0x14001065b  push    rdi
0x14001065c  push    r12
0x14001065e  push    r14
0x140010660  push    r15
0x140010662  sub     rsp, 40h
0x140010666  mov     rax, [rdx+0B8h]
0x14001066d  mov     rbp, rdx
0x140010670  mov     r15, [rcx+0E8h]
0x140010677  xor     ebx, ebx
0x140010679  mov     rdi, rcx
0x14001067c  movzx   edx, byte ptr [rax+1]
0x140010680  cmp     edx, 9
0x140010683  ja      loc_140010860
0x140010689  jz      loc_140010853
0x14001068f  mov     ecx, edx
0x140010691  test    edx, edx
0x140010693  jz      loc_140010797
0x140010699  sub     ecx, 1
0x14001069c  jz      loc_140010ACC
0x1400106a2  sub     ecx, 1
0x1400106a5  jz      short loc_140010716
0x1400106a7  sub     ecx, 1
0x1400106aa  jz      loc_140010ACC
0x1400106b0  sub     ecx, 1
0x1400106b3  jz      short loc_1400106F9
0x1400106b5  sub     ecx, 1
0x1400106b8  jz      loc_140010ACC
0x1400106be  sub     ecx, 1
0x1400106c1  jz      loc_140010ACC
0x1400106c7  sub     ecx, 1
0x1400106ca  jz      short loc_1400106E7
0x1400106cc  cmp     ecx, 1
0x1400106cf  jnz     loc_1400108A6
0x1400106d5  mov     rdx, rbp
0x1400106d8  mov     rcx, rdi
0x1400106db  call    HandlePdoQueryInterface
0x1400106e0  mov     esi, eax
0x1400106e2  jmp     loc_140010ADB
0x1400106e7  mov     rdx, rbp
0x1400106ea  mov     rcx, rdi
0x1400106ed  call    QueryFunctionDeviceRelations
0x1400106f2  mov     esi, eax
0x1400106f4  jmp     loc_140010ACE
0x1400106f9  cmp     dword ptr [rdi+14h], 2
0x1400106fd  jnz     loc_140010ACC
0x140010703  mov     dword ptr [rdi+18h], 2
0x14001070a  mov     dword ptr [rdi+14h], 6
0x140010711  jmp     loc_140010ACC
0x140010716  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x14001071b  test    eax, eax
0x14001071d  jz      short loc_14001076B
0x14001071f  lea     rsi, [rdi+1A0h]
0x140010726  mov     rcx, rsi; SpinLock
0x140010729  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010730  nop     dword ptr [rax+rax+00h]
0x140010735  mov     rcx, [rdi+1A8h]
0x14001073c  mov     r14b, al
0x14001073f  test    rcx, rcx
0x140010742  jz      short loc_140010757
0x140010744  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14001074b  nop     dword ptr [rax+rax+00h]
0x140010750  mov     [rdi+1A8h], rbx
0x140010757  mov     dl, r14b; NewIrql
0x14001075a  mov     rcx, rsi; SpinLock
0x14001075d  call    cs:__imp_KeReleaseSpinLock
0x140010764  nop     dword ptr [rax+rax+00h]
0x140010769  jmp     short loc_14001078A
0x14001076b  mov     rcx, [rdi+1A8h]
0x140010772  test    rcx, rcx
0x140010775  jz      short loc_14001078A
0x140010777  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14001077e  nop     dword ptr [rax+rax+00h]
0x140010783  mov     [rdi+1A8h], rbx
0x14001078a  mov     rcx, rdi; PeekContext
0x14001078d  call    PdoRemoveDevice
0x140010792  jmp     loc_1400106F2
0x140010797  mov     rdx, rdi
0x14001079a  mov     rcx, r15
0x14001079d  call    ResetPdoExtension
0x1400107a2  mov     dl, 1
0x1400107a4  mov     rcx, r15
0x1400107a7  call    CancelFdoIdleIrp
0x1400107ac  mov     eax, [rdi+14h]
0x1400107af  mov     [rdi+18h], eax
0x1400107b2  mov     dword ptr [rdi+14h], 2
0x1400107b9  test    eax, eax
0x1400107bb  jnz     short loc_140010820
0x1400107bd  mov     rcx, [rdi+0E0h]
0x1400107c4  lea     rdx, [rsp+68h+arg_0]
0x1400107c9  mov     [rsp+68h+arg_0], bl
0x1400107cd  call    GetD3Policy
0x1400107d2  test    eax, eax
0x1400107d4  js      short loc_140010820
0x1400107d6  cmp     [rsp+68h+arg_0], 1
0x1400107db  jnz     short loc_140010820
0x1400107dd  mov     r8, [r15+558h]
0x1400107e4  lea     rsi, [r15+208h]
0x1400107eb  mov     rcx, rsi; Object
0x1400107ee  lea     rdx, aD3coldstatemut; "D3ColdStateMutex"
0x1400107f5  call    AcquireMutex
0x1400107fa  mov     byte ptr [rdi+75h], 1
0x1400107fe  cmp     [r15+1B9h], bl
0x140010805  jz      short loc_14001080F
0x140010807  mov     rcx, r15
0x14001080a  call    ChangeParentD3ColdStateLocked
0x14001080f  xor     edx, edx; Wait
0x140010811  mov     rcx, rsi; Mutex
0x140010814  call    cs:__imp_KeReleaseMutex
0x14001081b  nop     dword ptr [rax+rax+00h]
0x140010820  cmp     [r15+552h], bl
0x140010827  jz      loc_140010ACC
0x14001082d  mov     rax, [rdi+180h]
0x140010834  cmp     [rax+3Bh], bl
0x140010837  jz      loc_140010ACC
0x14001083d  mov     r8d, 2
0x140010843  mov     rdx, rdi
0x140010846  mov     rcx, r15
0x140010849  call    LockSyncSendSetFeatureControlRequestForFunctionSuspend
0x14001084e  jmp     loc_140010ACC
0x140010853  mov     rdx, rbp
0x140010856  call    QueryFunctionCapabilities
0x14001085b  jmp     loc_1400106F2
0x140010860  mov     ecx, edx
0x140010862  sub     ecx, 0Bh
0x140010865  jz      loc_140010AAC
0x14001086b  sub     ecx, 1
0x14001086e  jz      loc_140010A9C
0x140010874  sub     ecx, 7
0x140010877  jz      loc_140010A8C
0x14001087d  sub     ecx, 1
0x140010880  jz      loc_140010A4D
0x140010886  sub     ecx, 1
0x140010889  jz      loc_140010A04
0x14001088f  sub     ecx, 1
0x140010892  jz      loc_1400109F4
0x140010898  sub     ecx, 1
0x14001089b  jz      loc_140010989
0x1400108a1  cmp     ecx, 2
0x1400108a4  jz      short loc_1400108EF
0x1400108a6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400108ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400108b4  jz      short loc_1400108E7
0x1400108b6  mov     rax, cs:WPP_GLOBAL_Control
0x1400108bd  cmp     [rax+48h], bx
0x1400108c1  jz      short loc_1400108E7
0x1400108c3  mov     rax, [rdi+0E0h]
0x1400108ca  mov     r9d, 26h ; '&'
0x1400108d0  mov     rcx, [rdi+188h]
0x1400108d7  mov     [rsp+68h+var_38], dl
0x1400108db  mov     dl, 5
0x1400108dd  mov     [rsp+68h+var_40], rax
0x1400108e2  call    WPP_RECORDER_SF_qc
0x1400108e7  mov     esi, [rbp+30h]
0x1400108ea  jmp     loc_140010ACE
0x1400108ef  mov     rcx, cs:g_SleepstudyLibraryHandle
0x1400108f6  mov     esi, ebx
0x1400108f8  test    rcx, rcx
0x1400108fb  jz      loc_140010ACE
0x140010901  lea     r14, [rdi+1A8h]
0x140010908  cmp     [r14], rbx
0x14001090b  jnz     loc_140010ACE
0x140010911  mov     r8, [rdi+0E0h]
0x140010918  mov     r9, r14
0x14001091b  mov     rdx, [r15+18h]
0x14001091f  call    cs:__imp_SleepstudyHelper_RegisterPdoWithParentPdo
0x140010926  nop     dword ptr [rax+rax+00h]
0x14001092b  mov     esi, eax
0x14001092d  test    eax, eax
0x14001092f  jns     short loc_140010975
0x140010931  mov     [r14], rbx
0x140010934  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001093b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010942  jz      loc_140010ACE
0x140010948  mov     rcx, [rdi+188h]
0x14001094f  lea     rax, WPP_54beca300c4a353e079921b0991edb26_Traceguids
0x140010956  mov     r9d, 25h ; '%'
0x14001095c  mov     dword ptr [rsp+68h+var_40], esi
0x140010960  mov     dl, 3
0x140010962  mov     [rsp+68h+var_48], rax
0x140010967  lea     r8d, [r9-1Dh]
0x14001096b  call    WPP_RECORDER_SF_d
0x140010970  jmp     loc_140010ACE
0x140010975  mov     rcx, [r14]
0x140010978  call    cs:__imp_SleepstudyHelper_ComponentActive
0x14001097f  nop     dword ptr [rax+rax+00h]
0x140010984  jmp     loc_140010ACE
0x140010989  mov     eax, [rdi+14h]
0x14001098c  mov     esi, ebx
0x14001098e  mov     [rdi+18h], eax
0x140010991  mov     dword ptr [rdi+14h], 9
0x140010998  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x14001099d  test    eax, eax
0x14001099f  jz      loc_140010ACE
0x1400109a5  lea     r14, [rdi+1A0h]
0x1400109ac  mov     rcx, r14; SpinLock
0x1400109af  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400109b6  nop     dword ptr [rax+rax+00h]
0x1400109bb  mov     rcx, [rdi+1A8h]
0x1400109c2  mov     r12b, al
0x1400109c5  test    rcx, rcx
0x1400109c8  jz      short loc_1400109DD
0x1400109ca  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x1400109d1  nop     dword ptr [rax+rax+00h]
0x1400109d6  mov     [rdi+1A8h], rbx
0x1400109dd  mov     dl, r12b; NewIrql
0x1400109e0  mov     rcx, r14; SpinLock
0x1400109e3  call    cs:__imp_KeReleaseSpinLock
0x1400109ea  nop     dword ptr [rax+rax+00h]
0x1400109ef  jmp     loc_140010ACE
0x1400109f4  mov     rdx, rbp
0x1400109f7  mov     rcx, rdi
0x1400109fa  call    HandlePdoDeviceUsageNotification
0x1400109ff  jmp     loc_1400106E0
0x140010a04  mov     edx, 18h
0x140010a09  mov     ecx, 100h
0x140010a0e  mov     r8d, 43627355h
0x140010a14  call    cs:__imp_ExAllocatePool2
0x140010a1b  nop     dword ptr [rax+rax+00h]
0x140010a20  test    rax, rax
0x140010a23  jz      short loc_140010A3C
0x140010a25  movups  xmm0, xmmword ptr cs:GUID_BUS_TYPE_USB.Data1
0x140010a2c  mov     qword ptr [rax+10h], 0Fh
0x140010a34  mov     esi, ebx
0x140010a36  movdqu  xmmword ptr [rax], xmm0
0x140010a3a  jmp     short loc_140010A44
0x140010a3c  mov     esi, 0C000009Ah
0x140010a41  mov     rax, rbx
0x140010a44  mov     [rbp+38h], rax
0x140010a48  jmp     loc_140010ACE
0x140010a4d  cmp     byte ptr [r15+560h], 1
0x140010a55  jnz     short loc_140010A67
0x140010a57  cmp     byte ptr [rdi+197h], 1
0x140010a5e  jnz     short loc_140010A67
0x140010a60  or      qword ptr [rbp+38h], 4
0x140010a65  jmp     short loc_140010ACC
0x140010a67  mov     ecx, [rdi+14h]
0x140010a6a  sub     ecx, 3
0x140010a6d  jz      short loc_140010A60
0x140010a6f  sub     ecx, 3
0x140010a72  jz      short loc_140010A85
0x140010a74  sub     ecx, 1
0x140010a77  jz      short loc_140010A7E
0x140010a79  cmp     ecx, 1
0x140010a7c  jnz     short loc_140010ACC
0x140010a7e  or      qword ptr [rbp+38h], 8
0x140010a83  jmp     short loc_140010ACC
0x140010a85  or      qword ptr [rbp+38h], 1
0x140010a8a  jmp     short loc_140010ACC
0x140010a8c  mov     rdx, rbp
0x140010a8f  mov     rcx, rdi
0x140010a92  call    QueryFunctionPdoID
0x140010a97  jmp     loc_1400106F2
0x140010a9c  mov     rdx, rbp
0x140010a9f  mov     rcx, rdi
0x140010aa2  call    GetDeviceText
0x140010aa7  jmp     loc_1400106F2
0x140010aac  mov     rcx, rdi
0x140010aaf  call    InstallExtPropDesc
0x140010ab4  mov     rcx, rdi
0x140010ab7  call    QuerySelectiveSuspendRegistryFlag
0x140010abc  mov     rcx, rdi
0x140010abf  call    QueryAllowIdleIrpInD3RegistryFlag
0x140010ac4  mov     rcx, rdi
0x140010ac7  call    QueryEndpointPriorities
0x140010acc  mov     esi, ebx
0x140010ace  mov     r8, rbp
0x140010ad1  mov     edx, esi
0x140010ad3  mov     rcx, r15
0x140010ad6  call    UsbcCompleteIrp
0x140010adb  lea     r11, [rsp+68h+var_28]
0x140010ae0  mov     eax, esi
0x140010ae2  mov     rbx, [r11+38h]
0x140010ae6  mov     rbp, [r11+40h]
0x140010aea  mov     rsp, r11
0x140010aed  pop     r15
0x140010aef  pop     r14
0x140010af1  pop     r12
0x140010af3  pop     rdi
0x140010af4  pop     rsi
0x140010af5  retn
```
