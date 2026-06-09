# SLpTriggerServiceWorker

- ea: `0x18000ea10`
- end: `0x18000eba2`
- name: `SLpTriggerServiceWorker`
- size: `402`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001ec0`
- `0x180002bf0`
- `0x180003410`
- `0x1800052b4`
- `0x1800052e0`
- `0x180006844`
- `0x180006c74`
- `0x18000a8d0`
- `0x18000d398`
- `0x18000ea10`
- `0x18000eeb0`
- `0x180014f50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ea60`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ea60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ea54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ea54`

## string_xrefs

- `0x18000ead7`: `SppNotificationCommandLine`
- `0x18000eb2d`: `TaskNotification`

## pseudocode

```c
__int64 __fastcall SLpTriggerServiceWorker(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  int v4; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rsi
  DWORD pSessionId; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  __int128 v16; // [rsp+48h] [rbp-30h] BYREF
  __int128 v17; // [rsp+58h] [rbp-20h]
  unsigned int v18; // [rsp+B4h] [rbp+3Ch]

  v18 = HIDWORD(a3);
  v15 = 0;
  pSessionId = 0;
  v3 = a3;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  if ( !a3 )
  {
    v4 = -2147024809;
LABEL_13:
    v10 = (unsigned int)v4;
    goto LABEL_14;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    pSessionId = -1;
  v7 = sub_18000D398((__int64)&v15, v6, 0);
  v4 = v7;
  if ( v7 < 0 )
    goto LABEL_6;
  v7 = sub_180006C74(v9, v8, &v14);
  v4 = v7;
  if ( v7 < 0
    || (v11 = v14,
        *(_QWORD *)&v16 = L"SppNotificationSessionId",
        LODWORD(v17) = pSessionId,
        DWORD2(v16) = 1,
        v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v14 + 72LL))(v14, &v16, 0),
        v4 = v7,
        v7 < 0) )
  {
LABEL_6:
    v10 = (unsigned int)v7;
LABEL_14:
    sub_180006844(v10);
    goto LABEL_15;
  }
  DWORD2(v16) = 2;
  *(_QWORD *)&v16 = L"SppNotificationCommandLine";
  *(_QWORD *)&v17 = __PAIR64__(v18, v3);
  v4 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, &v16, 0);
  if ( v4 < 0 )
  {
    sub_180002BF0(&dword_180018A9C, byte_18001ECC8);
    goto LABEL_13;
  }
  v4 = SLCallServer(v15, (unsigned int)L"TaskNotification", 1, v11, 0);
  sub_180001EC0(&dword_180018E3C, byte_18001E378);
  if ( v4 < 0 )
  {
    sub_180003410(qword_180018B98, byte_18001E468);
    goto LABEL_13;
  }
LABEL_15:
  sub_18000A8D0((unsigned int)v4);
  sub_1800052E0(&v14);
  sub_1800052B4(&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ea10  mov     [rsp-20h+arg_10], r8
0x18000ea15  push    rbp
0x18000ea16  push    rbx
0x18000ea17  push    rsi
0x18000ea18  push    rdi
0x18000ea19  mov     rbp, rsp
0x18000ea1c  sub     rsp, 78h
0x18000ea20  mov     [rbp+var_38], 0
0x18000ea28  xorps   xmm0, xmm0
0x18000ea2b  mov     [rbp+pSessionId], 0
0x18000ea32  mov     rdi, r8
0x18000ea35  mov     [rbp+var_40], 0
0x18000ea3d  movups  [rbp+var_30], xmm0
0x18000ea41  movups  [rbp+var_20], xmm0
0x18000ea45  test    r8, r8
0x18000ea48  jnz     short loc_18000EA54
0x18000ea4a  mov     ebx, 80070057h
0x18000ea4f  jmp     loc_18000EB77
0x18000ea54  call    cs:GetCurrentProcessId
0x18000ea5a  mov     ecx, eax; dwProcessId
0x18000ea5c  lea     rdx, [rbp+pSessionId]; pSessionId
0x18000ea60  call    cs:ProcessIdToSessionId
0x18000ea66  test    eax, eax
0x18000ea68  jnz     short loc_18000EA71
0x18000ea6a  mov     [rbp+pSessionId], 0FFFFFFFFh
0x18000ea71  xor     r8d, r8d
0x18000ea74  lea     rcx, [rbp+var_38]
0x18000ea78  call    sub_18000D398
0x18000ea7d  mov     ebx, eax
0x18000ea7f  test    eax, eax
0x18000ea81  jns     short loc_18000EA8A
0x18000ea83  mov     ecx, eax
0x18000ea85  jmp     loc_18000EB79
0x18000ea8a  lea     r8, [rbp+var_40]
0x18000ea8e  call    sub_180006C74
0x18000ea93  mov     ebx, eax
0x18000ea95  test    eax, eax
0x18000ea97  js      short loc_18000EA83
0x18000ea99  mov     rsi, [rbp+var_40]
0x18000ea9d  lea     rax, aSppnotificatio; "SppNotificationSessionId"
0x18000eaa4  mov     qword ptr [rbp+var_30], rax
0x18000eaa8  mov     eax, [rbp+pSessionId]
0x18000eaab  mov     dword ptr [rbp+var_20], eax
0x18000eaae  mov     dword ptr [rbp+var_30+8], 1
0x18000eab5  mov     rax, [rsi]
0x18000eab8  mov     rbx, [rax+48h]
0x18000eabc  mov     rcx, rbx
0x18000eabf  call    cs:__guard_check_icall_fptr
0x18000eac5  xor     r8d, r8d
0x18000eac8  lea     rdx, [rbp+var_30]
0x18000eacc  mov     rcx, rsi
0x18000eacf  call    rbx
0x18000ead1  mov     ebx, eax
0x18000ead3  test    eax, eax
0x18000ead5  js      short loc_18000EA83
0x18000ead7  lea     rax, aSppnotificatio_0; "SppNotificationCommandLine"
0x18000eade  mov     dword ptr [rbp+var_30+8], 2
0x18000eae5  mov     qword ptr [rbp+var_30], rax
0x18000eae9  mov     eax, dword ptr [rbp+arg_10+4]
0x18000eaec  mov     dword ptr [rbp+var_20+4], eax
0x18000eaef  mov     dword ptr [rbp+var_20], edi
0x18000eaf2  mov     rax, [rsi]
0x18000eaf5  mov     rbx, [rax+48h]
0x18000eaf9  mov     rcx, rbx
0x18000eafc  call    cs:__guard_check_icall_fptr
0x18000eb02  xor     r8d, r8d
0x18000eb05  lea     rdx, [rbp+var_30]
0x18000eb09  mov     rcx, rsi
0x18000eb0c  call    rbx
0x18000eb0e  mov     ebx, eax
0x18000eb10  test    eax, eax
0x18000eb12  jns     short loc_18000EB29
0x18000eb14  lea     rdx, byte_18001ECC8
0x18000eb1b  lea     rcx, dword_180018A9C
0x18000eb22  call    sub_180002BF0
0x18000eb27  jmp     short loc_18000EB77
0x18000eb29  mov     rcx, [rbp+var_38]
0x18000eb2d  lea     rdx, aTasknotificati; "TaskNotification"
0x18000eb34  mov     r9, rsi
0x18000eb37  mov     [rsp+78h+var_58], 0
0x18000eb40  mov     r8d, 1
0x18000eb46  call    SLCallServer
0x18000eb4b  lea     rdx, byte_18001E378
0x18000eb52  mov     ebx, eax
0x18000eb54  lea     rcx, dword_180018E3C
0x18000eb5b  call    sub_180001EC0
0x18000eb60  test    ebx, ebx
0x18000eb62  jns     short loc_18000EB7E
0x18000eb64  lea     rdx, byte_18001E468
0x18000eb6b  lea     rcx, qword_180018B98
0x18000eb72  call    sub_180003410
0x18000eb77  mov     ecx, ebx
0x18000eb79  call    sub_180006844
0x18000eb7e  mov     ecx, ebx
0x18000eb80  call    sub_18000A8D0
0x18000eb85  lea     rcx, [rbp+var_40]
0x18000eb89  call    sub_1800052E0
0x18000eb8e  lea     rcx, [rbp+var_38]
0x18000eb92  call    sub_1800052B4
0x18000eb97  mov     eax, ebx
0x18000eb99  add     rsp, 78h
0x18000eb9d  pop     rdi
0x18000eb9e  pop     rsi
0x18000eb9f  pop     rbx
0x18000eba0  pop     rbp
0x18000eba1  retn
```
