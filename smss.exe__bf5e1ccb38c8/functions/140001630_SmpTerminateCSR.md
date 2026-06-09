# SmpTerminateCSR

- ea: `0x140001630`
- end: `0x140001875`
- name: `SmpTerminateCSR`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400031b0`
- `0x140005ac4`

## callees

- `0x1400010b0`
- `0x140001450`
- `0x140001630`
- `0x140001e40`
- `0x140003114`
- `0x14000aca0`
- `0x140017954`
- `0x140018154`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x140001716`
- `ntdll!NtWaitForSingleObject` at `0x140001716`
- `ntdll!NtTerminateProcess` at `0x1400016fe`
- `ntdll!NtTerminateProcess` at `0x1400016fe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001679`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140001679`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400016a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400016a1`

## pseudocode

```c
__int64 __fastcall SmpTerminateCSR(unsigned int a1)
{
  __int64 v2; // rbp
  _QWORD **v3; // rbx
  _QWORD *i; // rax
  _QWORD *v5; // r14
  _QWORD **v6; // r11
  _QWORD **v7; // rbx
  NTSTATUS v8; // edi
  __int64 ProcessId; // rax
  _QWORD *v11; // rax
  _QWORD **v12; // r8
  _QWORD *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // [rsp+30h] [rbp-58h] BYREF
  _QWORD **v19; // [rsp+38h] [rbp-50h]
  PVOID v20[9]; // [rsp+40h] [rbp-48h] BYREF

  v19 = &v18;
  v20[0] = 0;
  v18 = &v18;
  v2 = a1;
  v3 = (_QWORD **)(SmpKnownSubSysTable + 24LL * (a1 & 0x1F));
  v20[1] = v3;
  RtlAcquireSRWLockExclusive(v3 + 2);
LABEL_2:
  for ( i = *v3; i != v3; i = (_QWORD *)*i )
  {
    if ( *((_DWORD *)i - 2) == a1 )
    {
      v5 = i - 9;
      if ( i != (_QWORD *)72 )
      {
        while ( 1 )
        {
          if ( !(unsigned int)SmpCheckSubSysStatus(v5) )
          {
            _InterlockedIncrement((volatile signed __int32 *)v5);
            SmpWaitForStatusChange(v17, 0, (unsigned int *)v20);
            if ( (v5[1] & 4) != 0 )
            {
              SmpDereferenceKnownSubSys(v5);
              goto LABEL_2;
            }
            SmpDereferenceKnownSubSys(v5);
          }
          v12 = (_QWORD **)v5[9];
          v13 = v5 + 9;
          _InterlockedOr((volatile signed __int32 *)v5 + 2, 4u);
          v14 = v5[9];
          if ( *(_QWORD **)(v14 + 8) != v5 + 9
            || (v15 = (_QWORD *)v5[10], (_QWORD *)*v15 != v13)
            || (*v15 = v14, *(_QWORD *)(v14 + 8) = v15, v16 = v19, *v19 != &v18) )
          {
LABEL_10:
            __fastfail(3u);
          }
          v5[10] = v19;
          *v13 = &v18;
          *v16 = v13;
          v19 = (_QWORD **)(v5 + 9);
          if ( v12 != v3 )
          {
            v5 = v12 - 9;
            if ( *((_DWORD *)v12 - 2) == a1 )
              continue;
          }
          goto LABEL_6;
        }
      }
      break;
    }
  }
LABEL_6:
  RtlReleaseSRWLockExclusive(v3 + 2);
  if ( v18 != &v18 )
  {
    if ( (unsigned __int8)SmpSessionIdIsInitialSessions(a1) )
    {
      *(_OWORD *)v20 = 0;
      SmpSetCoreProcessIds(a1, v20);
      v6 = (_QWORD **)v18;
    }
    while ( 1 )
    {
      if ( v6[1] != &v18 )
        goto LABEL_10;
      v11 = *v6;
      if ( (_QWORD **)(*v6)[1] != v6 )
        goto LABEL_10;
      v18 = *v6;
      v7 = v6 - 9;
      v11[1] = &v18;
      v8 = NtTerminateProcess(*(v6 - 5), 0);
      if ( ((v8 + 0x80000000) & 0x80000000) == 0 && v8 != -1073741558 )
        break;
      v8 = NtWaitForSingleObject(v7[4], 0, 0);
      if ( v8 < 0 )
        goto LABEL_17;
LABEL_13:
      SmpDereferenceKnownSubSys(v7);
      v6 = (_QWORD **)v18;
      if ( v18 == &v18 )
        return 0;
    }
    ProcessId = SmpGetProcessId(v7[4]);
    SmLogFailureInt((__int64)"SmpTerminateProcessAndWait", 0x5Bu, ProcessId, 0, v8);
LABEL_17:
    SmLogFailureInt((__int64)"SmpTerminateCSR", 0xDDu, *((unsigned int *)v7 + 6), v2, v8);
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x140001630  push    rbx
0x140001632  push    rbp
0x140001633  push    rsi
0x140001634  push    rdi
0x140001635  push    r14
0x140001637  push    r15
0x140001639  sub     rsp, 58h
0x14000163d  mov     esi, ecx
0x14000163f  lea     rax, [rsp+88h+var_58]
0x140001644  mov     [rsp+88h+var_50], rax
0x140001649  xor     ecx, ecx
0x14000164b  lea     rax, [rsp+88h+var_58]
0x140001650  mov     [rsp+88h+var_48], rcx
0x140001655  mov     [rsp+88h+var_58], rax
0x14000165a  mov     ebp, esi
0x14000165c  mov     eax, esi
0x14000165e  and     eax, 1Fh
0x140001661  lea     rdx, [rax+rax*2]
0x140001665  mov     rax, cs:SmpKnownSubSysTable
0x14000166c  lea     rbx, [rax+rdx*8]
0x140001670  lea     rcx, [rbx+10h]
0x140001674  mov     [rsp+88h+var_48+8], rbx
0x140001679  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14000167f  mov     rax, [rbx]
0x140001682  cmp     rax, rbx
0x140001685  jz      short loc_14000169D
0x140001687  cmp     [rax-8], esi
0x14000168a  jnz     loc_140001792
0x140001690  lea     r14, [rax-48h]
0x140001694  test    r14, r14
0x140001697  jnz     loc_140001819
0x14000169d  lea     rcx, [rbx+10h]
0x1400016a1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400016a7  mov     r11, [rsp+88h+var_58]
0x1400016ac  lea     rax, [rsp+88h+var_58]
0x1400016b1  cmp     r11, rax
0x1400016b4  jz      loc_140001739
0x1400016ba  mov     ecx, esi
0x1400016bc  call    SmpSessionIdIsInitialSessions
0x1400016c1  test    al, al
0x1400016c3  jnz     loc_140001853
0x1400016c9  mov     esi, 80000000h
0x1400016ce  xchg    ax, ax
0x1400016d0  lea     rax, [rsp+88h+var_58]
0x1400016d5  cmp     [r11+8], rax
0x1400016d9  jz      loc_14000179A
0x1400016df  mov     ecx, 3
0x1400016e4  int     29h; Win8: RtlFailFast(ecx)
0x1400016e6  mov     [rsp+88h+var_58], rax
0x1400016eb  lea     rcx, [rsp+88h+var_58]
0x1400016f0  lea     rbx, [r11-48h]
0x1400016f4  mov     [rax+8], rcx
0x1400016f8  mov     rcx, [rbx+20h]; ProcessHandle
0x1400016fc  xor     edx, edx; ExitStatus
0x1400016fe  call    cs:__imp_NtTerminateProcess
0x140001704  mov     edi, eax
0x140001706  lea     ecx, [rax+rsi]
0x140001709  test    esi, ecx
0x14000170b  jz      short loc_140001748
0x14000170d  mov     rcx, [rbx+20h]; Object
0x140001711  xor     r8d, r8d; Timeout
0x140001714  xor     edx, edx; Alertable
0x140001716  call    cs:__imp_NtWaitForSingleObject
0x14000171c  mov     edi, eax
0x14000171e  test    eax, eax
0x140001720  js      short loc_140001774
0x140001722  mov     rcx, rbx; BaseAddress
0x140001725  call    SmpDereferenceKnownSubSys
0x14000172a  mov     r11, [rsp+88h+var_58]
0x14000172f  lea     rax, [rsp+88h+var_58]
0x140001734  cmp     r11, rax
0x140001737  jnz     short loc_1400016D0
0x140001739  xor     eax, eax
0x14000173b  add     rsp, 58h
0x14000173f  pop     r15
0x140001741  pop     r14
0x140001743  pop     rdi
0x140001744  pop     rsi
0x140001745  pop     rbp
0x140001746  pop     rbx
0x140001747  retn
0x140001748  cmp     edi, 0C000010Ah
0x14000174e  jz      short loc_14000170D
0x140001750  mov     rcx, [rbx+20h]
0x140001754  call    SmpGetProcessId
0x140001759  mov     r8, rax
0x14000175c  mov     [rsp+88h+var_68], edi
0x140001760  xor     r9d, r9d
0x140001763  lea     rcx, aSmpterminatepr; "SmpTerminateProcessAndWait"
0x14000176a  mov     edx, 5Bh ; '['
0x14000176f  call    SmLogFailureInt
0x140001774  mov     r8d, [rbx+18h]
0x140001778  lea     rcx, aSmpterminatecs; "SmpTerminateCSR"
0x14000177f  mov     r9, rbp
0x140001782  mov     [rsp+88h+var_68], edi
0x140001786  mov     edx, 0DDh
0x14000178b  call    SmLogFailureInt
0x140001790  jmp     short loc_140001722
0x140001792  mov     rax, [rax]
0x140001795  jmp     loc_140001682
0x14000179a  mov     rax, [r11]
0x14000179d  cmp     [rax+8], r11
0x1400017a1  jnz     loc_1400016DF
0x1400017a7  jmp     loc_1400016E6
0x1400017ac  mov     r8, [r14+48h]
0x1400017b0  lea     rax, [r14+48h]
0x1400017b4  lock or dword ptr [r14+8], 4
0x1400017ba  mov     rdx, [rax]
0x1400017bd  cmp     [rdx+8], rax
0x1400017c1  jnz     loc_1400016DF
0x1400017c7  mov     rcx, [r14+50h]
0x1400017cb  cmp     [rcx], rax
0x1400017ce  jnz     loc_1400016DF
0x1400017d4  mov     [rcx], rdx
0x1400017d7  mov     [rdx+8], rcx
0x1400017db  lea     rdx, [rsp+88h+var_58]
0x1400017e0  mov     rcx, [rsp+88h+var_50]
0x1400017e5  cmp     [rcx], rdx
0x1400017e8  jnz     loc_1400016DF
0x1400017ee  mov     [rax+8], rcx
0x1400017f2  lea     rdx, [rsp+88h+var_58]
0x1400017f7  mov     [rax], rdx
0x1400017fa  mov     [rcx], rax
0x1400017fd  mov     [rsp+88h+var_50], rax
0x140001802  cmp     r8, rbx
0x140001805  jz      loc_14000169D
0x14000180b  cmp     [r8-8], esi
0x14000180f  lea     r14, [r8-48h]
0x140001813  jnz     loc_14000169D
0x140001819  mov     rcx, r14
0x14000181c  call    SmpCheckSubSysStatus
0x140001821  test    eax, eax
0x140001823  jnz     short loc_1400017AC
0x140001825  lock inc dword ptr [r14]
0x140001829  lea     r8, [rsp+88h+var_48]
0x14000182e  xor     edx, edx
0x140001830  call    SmpWaitForStatusChange
0x140001835  test    byte ptr [r14+8], 4
0x14000183a  mov     rcx, r14; BaseAddress
0x14000183d  jnz     short loc_140001849
0x14000183f  call    SmpDereferenceKnownSubSys
0x140001844  jmp     loc_1400017AC
0x140001849  call    SmpDereferenceKnownSubSys
0x14000184e  jmp     loc_14000167F
0x140001853  xorps   xmm0, xmm0
0x140001856  lea     rdx, [rsp+88h+var_48]
0x14000185b  mov     r8b, 1
0x14000185e  mov     ecx, esi
0x140001860  movdqu  xmmword ptr [rsp+88h+var_48], xmm0
0x140001866  call    SmpSetCoreProcessIds
0x14000186b  mov     r11, [rsp+88h+var_58]
0x140001870  jmp     loc_1400016C9
```
