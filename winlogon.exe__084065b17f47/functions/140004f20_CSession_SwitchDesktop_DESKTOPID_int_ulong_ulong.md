# CSession::SwitchDesktop(_DESKTOPID,int *,ulong,ulong)

- ea: `0x140004f20`
- end: `0x140005658`
- name: `?SwitchDesktop@CSession@@QEAAXW4_DESKTOPID@@PEAHKK@Z`
- size: `1848`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003b60`
- `0x140003ea0`
- `0x1400043d0`
- `0x140004470`
- `0x1400045d0`
- `0x140004e80`
- `0x140006c3c`
- `0x1400176f8`
- `0x14003c7b8`
- `0x1400505c4`
- `0x14005f5e0`
- `0x14005f6d0`
- `0x14005f964`
- `0x140063ba0`
- `0x140071140`
- `0x140071ef0`
- `0x1400858e0`
- `0x1400877f0`

## callees

- `0x140004f20`
- `0x1400057f4`
- `0x14000fb30`
- `0x14001a200`
- `0x140041c34`
- `0x14004df08`
- `0x14004ea3c`
- `0x14005ec90`
- `0x14005fb84`
- `0x1400789c0`
- `0x14007a9bc`
- `0x14007d90c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005325`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400053ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400053e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005325`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400053ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400053e2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000500e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000500e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000510b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400052bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000510b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400052bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000517c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005365`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000517c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005365`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400050fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000516e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400052ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400050fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000516e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400052ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004fea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000545c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004fea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000545c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055c1`
- `ntdll!NtSetInformationThread` at `0x140004fcb`
- `ntdll!NtSetInformationThread` at `0x14000503a`
- `ntdll!NtSetInformationThread` at `0x140004fcb`
- `ntdll!NtSetInformationThread` at `0x14000503a`
- `ext-ms-win-ntuser-private-l1-1-0!SwitchDesktopWithFade` at `0x140005384`
- `ext-ms-win-ntuser-private-l1-1-0!SwitchDesktopWithFade` at `0x140005384`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x14000523e`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x14000523e`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x1400051b4`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x1400051b4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SwitchDesktop` at `0x140004fe0`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SwitchDesktop` at `0x140004fe0`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x14000518a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1400051c7`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140005337`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140005618`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x14009cd5a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x14000518a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1400051c7`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140005337`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x140005618`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x14009cd5a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1400050e6`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14000513c`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x140005298`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1400052ee`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1400050e6`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14000513c`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x140005298`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1400052ee`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x1400050a3`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x14000524e`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x1400050a3`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x14000524e`

## pseudocode

```c
int __fastcall CSession::SwitchDesktop(__int64 a1, int a2, int *a3, unsigned int a4, unsigned int a5)
{
  int *v6; // r12
  int v9; // esi
  int v10; // r14d
  int v11; // ecx
  void *v12; // rax
  HDESK v13; // rdi
  CUser *v14; // rcx
  unsigned int v15; // esi
  NTSTATUS v16; // r14d
  DWORD LastError; // eax
  unsigned int v19; // edi
  HDESK v20; // r14
  DWORD v21; // edi
  HANDLE v22; // rax
  void *v23; // rdi
  HANDLE v24; // rax
  HDESK v25; // rcx
  __int64 v26; // rdx
  HDESK v27; // r12
  DWORD v28; // edi
  HANDLE ProcessHeap; // rax
  void *v30; // rdi
  __int64 v31; // r9
  HANDLE v32; // rax
  DWORD v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  DWORD v36; // eax
  HDESK v37; // rcx
  int v39; // [rsp+58h] [rbp-98h]
  int v40; // [rsp+5Ch] [rbp-94h] BYREF
  DWORD nLength; // [rsp+60h] [rbp-90h] BYREF
  int ThreadInformation; // [rsp+64h] [rbp-8Ch] BYREF
  DWORD nLengthNeeded; // [rsp+68h] [rbp-88h] BYREF
  int v44; // [rsp+6Ch] [rbp-84h]
  int v45; // [rsp+70h] [rbp-80h]
  _DWORD v46[2]; // [rsp+78h] [rbp-78h] BYREF
  void *v47; // [rsp+80h] [rbp-70h] BYREF
  void *v48; // [rsp+88h] [rbp-68h] BYREF
  DWORD v49; // [rsp+90h] [rbp-60h] BYREF
  unsigned int v50; // [rsp+94h] [rbp-5Ch]
  DWORD lpnLengthNeeded; // [rsp+98h] [rbp-58h] BYREF
  HDESK v52; // [rsp+A0h] [rbp-50h]
  int v53; // [rsp+A8h] [rbp-48h]
  int v54; // [rsp+100h] [rbp+10h] BYREF
  int *v55; // [rsp+108h] [rbp+18h]

  v55 = a3;
  v54 = a2;
  v6 = a3;
  v9 = 87;
  v40 = 87;
  v10 = 0;
  v11 = 0;
  v39 = 0;
  LODWORD(v12) = *(_DWORD *)(a1 + 144);
  if ( (_DWORD)v12 != a2 )
  {
    if ( (_DWORD)v12 == 2 )
    {
      LockWindowStation(*(_QWORD *)(a1 + 96));
      v27 = OpenInputDesktop(0, 0, 0x2000000u);
      *(_QWORD *)(a1 + 112) = v27;
      v39 = 1;
      nLength = 0;
      v49 = 0;
      v44 = 0;
      v47 = 0;
      GetUserObjectInformationW(v27, 2, 0, 0, &nLength);
      LODWORD(v12) = nLength;
      if ( nLength )
      {
        v28 = nLength;
        ProcessHeap = GetProcessHeap();
        v12 = HeapAlloc(ProcessHeap, 8u, v28);
        v30 = v12;
        v47 = v12;
        if ( v12 && (LODWORD(v12) = GetUserObjectInformationW(v27, 2, v12, nLength, &v49), (_DWORD)v12) )
        {
          v44 = 1;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_qS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              (unsigned int)WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids,
              *(_QWORD *)(a1 + 112),
              (__int64)v30);
          }
          if ( !(unsigned int)_o__wcsicmp(v30, L"Disconnected")
            || !(unsigned int)_o__wcsicmp(v30, L"Winlogon")
            || !(unsigned int)_o__wcsicmp(v30, L"Screen-saver") )
          {
            CloseDesktop(*(HDESK *)(a1 + 112));
            v39 = 0;
            *(_QWORD *)(a1 + 112) = 0;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v31);
            }
          }
          v32 = GetProcessHeap();
          LODWORD(v12) = HeapFree(v32, 0, v30);
          v47 = 0;
        }
        else if ( v30 )
        {
          LODWORD(v12) = UHHeapFree(&v47);
        }
      }
    }
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v13 = *(HDESK *)(a1 + 136);
        v52 = v13;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_5;
        }
        v26 = 43;
      }
      else
      {
        if ( a2 != 2 )
          goto LABEL_60;
        v13 = *(HDESK *)(a1 + 112);
        if ( !v13 )
          v13 = *(HDESK *)(a1 + 120);
        v52 = v13;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
LABEL_5:
          v15 = 0;
          v50 = 0;
          ThreadInformation = 1;
          v16 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadLastSystemCall|0x20, &ThreadInformation, 4u);
          while ( !(a4 ? SwitchDesktopWithFade(v13, a4, a5) : SwitchDesktop(v13)) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_DD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids,
                LastError,
                a4);
            }
            if ( v15 < 0xA )
              v50 = ++v15;
            Sleep(100 * v15);
          }
          if ( !v16 )
          {
            ThreadInformation = 0;
            v19 = NtSetInformationThread(
                    (HANDLE)0xFFFFFFFFFFFFFFFELL,
                    ThreadLastSystemCall|0x20,
                    &ThreadInformation,
                    4u);
            if ( v19 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, v19);
            }
          }
          v9 = 0;
          v40 = 0;
          WinlogonProvider::ResilientSwitchDesktopWithFade<enum _DESKTOPID &,unsigned long &>(&v54, &v40);
          v48 = 0;
          v20 = OpenInputDesktop(0, 0, 0x2000000u);
          if ( !v20 )
          {
            LODWORD(v12) = (_DWORD)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v36 = GetLastError();
              LODWORD(v12) = WPP_SF_d(
                               *((_QWORD *)WPP_GLOBAL_Control + 2),
                               37,
                               WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids,
                               v36);
            }
LABEL_30:
            v10 = 1;
            v53 = 1;
            *(_DWORD *)(a1 + 144) = a2;
            if ( a2 == 2 )
            {
              LODWORD(v12) = UnlockWindowStation(*(_QWORD *)(a1 + 96));
              v25 = *(HDESK *)(a1 + 112);
              if ( v25 )
              {
                LODWORD(v12) = CloseDesktop(v25);
                *(_QWORD *)(a1 + 112) = 0;
                v11 = 0;
LABEL_33:
                v6 = v55;
                goto LABEL_85;
              }
            }
LABEL_60:
            v11 = v39;
            goto LABEL_33;
          }
          nLengthNeeded = 0;
          lpnLengthNeeded = 0;
          v45 = 0;
          v48 = 0;
          GetUserObjectInformationW(v20, 2, 0, 0, &nLengthNeeded);
          if ( nLengthNeeded )
          {
            v21 = nLengthNeeded;
            v22 = GetProcessHeap();
            v23 = HeapAlloc(v22, 8u, v21);
            v48 = v23;
            if ( v23 && GetUserObjectInformationW(v20, 2, v23, nLengthNeeded, &lpnLengthNeeded) )
            {
              v45 = 1;
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v23);
              }
              v24 = GetProcessHeap();
              HeapFree(v24, 0, v23);
              v48 = 0;
LABEL_29:
              LODWORD(v12) = CloseDesktop(v20);
              goto LABEL_30;
            }
            if ( v23 )
              UHHeapFree(&v48);
          }
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v33 = GetLastError();
            WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, v35, v20, v33);
          }
          goto LABEL_29;
        }
        v26 = 42;
      }
    }
    else
    {
      v13 = *(HDESK *)(a1 + 128);
      v52 = v13;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_5;
      }
      v26 = 41;
    }
    WPP_SF_q(*((_QWORD *)v14 + 2), v26, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v13);
    goto LABEL_5;
  }
  v9 = 0;
  v40 = 0;
LABEL_85:
  if ( v9 )
  {
    if ( v11 )
    {
      v37 = *(HDESK *)(a1 + 112);
      if ( v37 )
      {
        CloseDesktop(v37);
        *(_QWORD *)(a1 + 112) = 0;
      }
    }
    v46[0] = v9;
    v46[1] = a2;
    LODWORD(v12) = CGlobalStore::ReportApplicationEvent(*(CGlobalStore **)(a1 + 80), 1u, 0xC0000FA3, 8u, v46, 0);
  }
  if ( v6 )
    *v6 = v10;
  return (int)v12;
}

```

## disassembly

```asm
0x140004f20  mov     [rsp+arg_10], r8
0x140004f25  mov     [rsp+arg_8], edx
0x140004f29  mov     [rsp+arg_0], rcx
0x140004f2e  push    rbx
0x140004f2f  push    rsi
0x140004f30  push    rdi
0x140004f31  push    r12
0x140004f33  push    r13
0x140004f35  push    r14
0x140004f37  push    r15
0x140004f39  sub     rsp, 90h
0x140004f40  mov     r13d, r9d
0x140004f43  mov     r12, r8
0x140004f46  mov     r15d, edx
0x140004f49  mov     rbx, rcx
0x140004f4c  mov     esi, 57h ; 'W'
0x140004f51  mov     [rsp+0C8h+var_94], esi
0x140004f55  xor     r14d, r14d
0x140004f58  xor     ecx, ecx
0x140004f5a  mov     [rsp+0C8h+var_98], ecx
0x140004f5e  mov     eax, [rbx+90h]
0x140004f64  cmp     eax, edx
0x140004f66  jz      loc_14000547E
0x140004f6c  cmp     eax, 2
0x140004f6f  jz      loc_14000523A
0x140004f75  lea     r12, WPP_GLOBAL_Control
0x140004f7c  mov     edi, 1
0x140004f81  test    r15d, r15d
0x140004f84  jnz     loc_1400051E5
0x140004f8a  mov     rdi, [rbx+80h]
0x140004f91  mov     [rsp+0C8h+var_50], rdi
0x140004f96  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f9d  cmp     rcx, r12
0x140004fa0  jnz     loc_14000538F
0x140004fa6  xor     esi, esi
0x140004fa8  mov     [rsp+0C8h+var_5C], esi
0x140004fac  mov     [rsp+0C8h+ThreadInformation], 1
0x140004fb4  mov     r9d, 4; ThreadInformationLength
0x140004fba  lea     r8, [rsp+0C8h+ThreadInformation]; ThreadInformation
0x140004fbf  mov     edx, 35h ; '5'; ThreadInformationClass
0x140004fc4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140004fcb  call    cs:__imp_NtSetInformationThread
0x140004fd1  mov     r14d, eax
0x140004fd4  mov     rcx, rdi; hDesktop
0x140004fd7  test    r13d, r13d
0x140004fda  jnz     loc_140005379
0x140004fe0  call    cs:__imp_SwitchDesktop
0x140004fe6  test    eax, eax
0x140004fe8  jnz     short loc_140005016
0x140004fea  call    cs:__imp_GetLastError
0x140004ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ff7  cmp     rcx, r12
0x140004ffa  jnz     loc_140005528
0x140005000  cmp     esi, 0Ah
0x140005003  jnb     short loc_14000500B
0x140005005  inc     esi
0x140005007  mov     [rsp+0C8h+var_5C], esi
0x14000500b  imul    ecx, esi, 64h ; 'd'; dwMilliseconds
0x14000500e  call    cs:__imp_Sleep
0x140005014  jmp     short loc_140004FD4
0x140005016  xor     r13d, r13d
0x140005019  test    r14d, r14d
0x14000501c  jnz     short loc_14000507A
0x14000501e  mov     [rsp+0C8h+ThreadInformation], r13d
0x140005023  mov     r9d, 4; ThreadInformationLength
0x140005029  lea     r8, [rsp+0C8h+ThreadInformation]; ThreadInformation
0x14000502e  mov     edx, 35h ; '5'; ThreadInformationClass
0x140005033  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14000503a  call    cs:__imp_NtSetInformationThread
0x140005040  mov     edi, eax
0x140005042  test    eax, eax
0x140005044  jnz     loc_14000555E
0x14000504a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005051  cmp     rcx, r12
0x140005054  jz      short loc_14000507A
0x140005056  test    byte ptr [rcx+1Ch], 4
0x14000505a  jz      short loc_14000507A
0x14000505c  cmp     byte ptr [rcx+19h], 2
0x140005060  jb      short loc_14000507A
0x140005062  mov     edx, 0Ch
0x140005067  mov     r9d, edi
0x14000506a  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x140005071  mov     rcx, [rcx+10h]
0x140005075  call    WPP_SF_d
0x14000507a  mov     esi, r13d
0x14000507d  mov     [rsp+0C8h+var_94], r13d
0x140005082  lea     rdx, [rsp+0C8h+var_94]
0x140005087  lea     rcx, [rsp+0C8h+arg_8]
0x14000508f  call    ??$ResilientSwitchDesktopWithFade@AEAW4_DESKTOPID@@AEAK@WinlogonProvider@@SAXAEAW4_DESKTOPID@@AEAK@Z; WinlogonProvider::ResilientSwitchDesktopWithFade<_DESKTOPID &,ulong &>(_DESKTOPID &,ulong &)
0x140005094  mov     [rsp+0C8h+var_68], r13
0x140005099  xor     edx, edx; fInherit
0x14000509b  xor     ecx, ecx; dwFlags
0x14000509d  mov     r8d, 2000000h; dwDesiredAccess
0x1400050a3  call    cs:__imp_OpenInputDesktop
0x1400050a9  mov     r14, rax
0x1400050ac  test    rax, rax
0x1400050af  jz      loc_14000559D
0x1400050b5  mov     [rsp+0C8h+nLengthNeeded], r13d
0x1400050ba  mov     [rsp+0C8h+var_58], r13d
0x1400050bf  mov     [rsp+0C8h+var_80], r13d
0x1400050c4  mov     [rsp+0C8h+var_80], r13d
0x1400050c9  mov     [rsp+0C8h+var_68], r13
0x1400050ce  lea     rax, [rsp+0C8h+nLengthNeeded]
0x1400050d3  mov     [rsp+0C8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1400050d8  xor     r9d, r9d; nLength
0x1400050db  xor     r8d, r8d; pvInfo
0x1400050de  mov     edx, 2; nIndex
0x1400050e3  mov     rcx, r14; hObj
0x1400050e6  call    cs:__imp_GetUserObjectInformationW
0x1400050ec  mov     eax, [rsp+0C8h+nLengthNeeded]
0x1400050f0  test    eax, eax
0x1400050f2  jz      loc_140005438
0x1400050f8  mov     edi, eax
0x1400050fa  call    cs:__imp_GetProcessHeap
0x140005100  mov     rcx, rax; hHeap
0x140005103  mov     r8d, edi; dwBytes
0x140005106  mov     edx, 8; dwFlags
0x14000510b  call    cs:__imp_HeapAlloc
0x140005111  mov     rdi, rax
0x140005114  mov     [rsp+0C8h+var_68], rax
0x140005119  test    rax, rax
0x14000511c  jz      loc_140005585
0x140005122  lea     rax, [rsp+0C8h+var_58]
0x140005127  mov     [rsp+0C8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14000512c  mov     r9d, [rsp+0C8h+nLengthNeeded]; nLength
0x140005131  mov     r8, rdi; pvInfo
0x140005134  mov     edx, 2; nIndex
0x140005139  mov     rcx, r14; hObj
0x14000513c  call    cs:__imp_GetUserObjectInformationW
0x140005142  test    eax, eax
0x140005144  jz      loc_140005585
0x14000514a  mov     [rsp+0C8h+var_80], 1
0x140005152  mov     rcx, cs:WPP_GLOBAL_Control
0x140005159  cmp     rcx, r12
0x14000515c  jz      short loc_14000516E
0x14000515e  test    byte ptr [rcx+1Ch], 10h
0x140005162  jz      short loc_14000516E
0x140005164  cmp     byte ptr [rcx+19h], 4
0x140005168  jnb     loc_140005568
0x14000516e  call    cs:__imp_GetProcessHeap
0x140005174  mov     r8, rdi; lpMem
0x140005177  xor     edx, edx; dwFlags
0x140005179  mov     rcx, rax; hHeap
0x14000517c  call    cs:__imp_HeapFree
0x140005182  mov     [rsp+0C8h+var_68], r13
0x140005187  mov     rcx, r14; hDesktop
0x14000518a  call    cs:__imp_CloseDesktop
0x140005190  mov     edi, 1
0x140005195  mov     r14d, edi
0x140005198  mov     [rsp+0C8h+var_48], edi
0x14000519f  mov     [rbx+90h], r15d
0x1400051a6  cmp     r15d, 2
0x1400051aa  jnz     loc_14000542F
0x1400051b0  mov     rcx, [rbx+60h]
0x1400051b4  call    cs:__imp_UnlockWindowStation
0x1400051ba  mov     rcx, [rbx+70h]; hDesktop
0x1400051be  test    rcx, rcx
0x1400051c1  jz      loc_14000542F
0x1400051c7  call    cs:__imp_CloseDesktop
0x1400051cd  mov     [rbx+70h], r13
0x1400051d1  mov     ecx, r13d
0x1400051d4  mov     [rsp+0C8h+var_98], ecx
0x1400051d8  mov     r12, [rsp+0C8h+arg_10]
0x1400051e0  jmp     loc_1400055EB
0x1400051e5  mov     ecx, r15d
0x1400051e8  sub     ecx, 1
0x1400051eb  jz      loc_1400054EE
0x1400051f1  cmp     ecx, 1
0x1400051f4  jnz     loc_14000542C
0x1400051fa  mov     rdi, [rbx+70h]
0x1400051fe  test    rdi, rdi
0x140005201  jz      loc_1400054E5
0x140005207  mov     [rsp+0C8h+var_50], rdi
0x14000520c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005213  cmp     rcx, r12
0x140005216  jz      loc_140004FA6
0x14000521c  test    byte ptr [rcx+1Ch], 10h
0x140005220  jz      loc_140004FA6
0x140005226  cmp     byte ptr [rcx+19h], 5
0x14000522a  jb      loc_140004FA6
0x140005230  mov     edx, 2Ah ; '*'
0x140005235  jmp     loc_1400053A8
0x14000523a  mov     rcx, [rbx+60h]
0x14000523e  call    cs:__imp_LockWindowStation
0x140005244  xor     edx, edx; fInherit
0x140005246  xor     ecx, ecx; dwFlags
0x140005248  mov     r8d, 2000000h; dwDesiredAccess
0x14000524e  call    cs:__imp_OpenInputDesktop
0x140005254  mov     r12, rax
0x140005257  mov     [rbx+70h], rax
0x14000525b  mov     edi, 1
0x140005260  mov     [rsp+0C8h+var_98], edi
0x140005264  xor     eax, eax
0x140005266  mov     [rsp+0C8h+var_70], rax
0x14000526b  mov     [rsp+0C8h+nLength], eax
0x14000526f  mov     [rsp+0C8h+var_60], eax
0x140005273  mov     [rsp+0C8h+var_84], eax
0x140005277  mov     [rsp+0C8h+var_84], eax
0x14000527b  mov     [rsp+0C8h+var_70], rax
0x140005280  lea     rax, [rsp+0C8h+nLength]
0x140005285  mov     [rsp+0C8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14000528a  xor     r9d, r9d; nLength
0x14000528d  xor     r8d, r8d; pvInfo
0x140005290  mov     edx, 2; nIndex
0x140005295  mov     rcx, r12; hObj
0x140005298  call    cs:__imp_GetUserObjectInformationW
0x14000529e  mov     eax, [rsp+0C8h+nLength]
0x1400052a2  test    eax, eax
0x1400052a4  jz      loc_1400054D9
0x1400052aa  mov     edi, eax
0x1400052ac  call    cs:__imp_GetProcessHeap
0x1400052b2  mov     rcx, rax; hHeap
0x1400052b5  mov     r8d, edi; dwBytes
0x1400052b8  mov     edx, 8; dwFlags
0x1400052bd  call    cs:__imp_HeapAlloc
0x1400052c3  mov     rdi, rax
0x1400052c6  mov     [rsp+0C8h+var_70], rax
0x1400052cb  test    rax, rax
0x1400052ce  jz      loc_1400054C1
0x1400052d4  lea     rax, [rsp+0C8h+var_60]
0x1400052d9  mov     [rsp+0C8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1400052de  mov     r9d, [rsp+0C8h+nLength]; nLength
0x1400052e3  mov     r8, rdi; pvInfo
0x1400052e6  mov     edx, 2; nIndex
0x1400052eb  mov     rcx, r12; hObj
0x1400052ee  call    cs:__imp_GetUserObjectInformationW
0x1400052f4  test    eax, eax
0x1400052f6  jz      loc_1400054C1
0x1400052fc  mov     [rsp+0C8h+var_84], 1
0x140005304  lea     r12, WPP_GLOBAL_Control
0x14000530b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005312  cmp     rcx, r12
0x140005315  jnz     loc_1400053F5
0x14000531b  lea     rdx, aDisconnected; "Disconnected"
0x140005322  mov     rcx, rdi
0x140005325  call    cs:__imp__o__wcsicmp
0x14000532b  test    eax, eax
0x14000532d  jnz     loc_1400053C0
0x140005333  mov     rcx, [rbx+70h]; hDesktop
0x140005337  call    cs:__imp_CloseDesktop
0x14000533d  xor     eax, eax
0x14000533f  mov     [rsp+0C8h+var_98], eax
0x140005343  mov     [rbx+70h], rax
0x140005347  mov     rcx, cs:WPP_GLOBAL_Control
0x14000534e  cmp     rcx, r12
0x140005351  jnz     loc_140005493
0x140005357  call    cs:__imp_GetProcessHeap
0x14000535d  mov     r8, rdi; lpMem
0x140005360  xor     edx, edx; dwFlags
0x140005362  mov     rcx, rax; hHeap
0x140005365  call    cs:__imp_HeapFree
0x14000536b  mov     [rsp+0C8h+var_70], 0
0x140005374  jmp     loc_140004F7C
0x140005379  mov     r8d, [rsp+0C8h+arg_20]
0x140005381  mov     edx, r13d
0x140005384  call    cs:__imp_SwitchDesktopWithFade
0x14000538a  jmp     loc_140004FE6
0x14000538f  test    byte ptr [rcx+1Ch], 10h
0x140005393  jz      loc_140004FA6
0x140005399  cmp     byte ptr [rcx+19h], 5
0x14000539d  jb      loc_140004FA6
0x1400053a3  mov     edx, 29h ; ')'
0x1400053a8  mov     r9, rdi
0x1400053ab  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x1400053b2  mov     rcx, [rcx+10h]
0x1400053b6  call    WPP_SF_q
0x1400053bb  jmp     loc_140004FA6
0x1400053c0  lea     rdx, aWinlogon_1; "Winlogon"
0x1400053c7  mov     rcx, rdi
0x1400053ca  call    cs:__imp__o__wcsicmp
0x1400053d0  test    eax, eax
0x1400053d2  jz      loc_140005333
0x1400053d8  lea     rdx, szDesktop; "Screen-saver"
0x1400053df  mov     rcx, rdi
0x1400053e2  call    cs:__imp__o__wcsicmp
0x1400053e8  test    eax, eax
0x1400053ea  jnz     loc_140005357
0x1400053f0  jmp     loc_140005333
0x1400053f5  test    byte ptr [rcx+1Ch], 10h
0x1400053f9  jz      loc_14000531B
0x1400053ff  cmp     byte ptr [rcx+19h], 4
0x140005403  jb      loc_14000531B
0x140005409  mov     edx, 27h ; '''
0x14000540e  mov     [rsp+0C8h+lpnLengthNeeded], rdi
0x140005413  mov     r9, [rbx+70h]
0x140005417  lea     r8, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14000541e  mov     rcx, [rcx+10h]
0x140005422  call    WPP_SF_qS
0x140005427  jmp     loc_14000531B
0x14000542c  xor     r13d, r13d
0x14000542f  mov     ecx, [rsp+0C8h+var_98]
0x140005433  jmp     loc_1400051D8
0x140005438  mov     rax, cs:WPP_GLOBAL_Control
0x14000543f  cmp     rax, r12
0x140005442  jz      loc_140005187
0x140005448  test    byte ptr [rax+1Ch], 10h
0x14000544c  jz      loc_140005187
0x140005452  cmp     byte ptr [rax+19h], 4
0x140005456  jb      loc_140005187
0x14000545c  call    cs:__imp_GetLastError
  ... truncated ...
```
