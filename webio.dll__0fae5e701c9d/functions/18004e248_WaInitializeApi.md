# WaInitializeApi

- ea: `0x18004e248`
- end: `0x18004e468`
- name: `WaInitializeApi`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fac8`

## callees

- `0x1800180e0`
- `0x18001f3d8`
- `0x18004e248`
- `0x18004e470`
- `0x18004e5a0`
- `0x18004e77c`
- `0x1800665d4`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004e309`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004e309`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e328`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e328`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e354`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e354`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x18004e2e7`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x18004e2e7`

## pseudocode

```c
__int64 __fastcall WaInitializeApi(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // rdi
  __int64 v4; // rsi
  char v6; // r12
  unsigned int ApiObject; // ebx
  __int64 CurrentProcessorNumber; // r14
  union _SLIST_HEADER *v9; // r13
  PSLIST_ENTRY v10; // rax
  PSLIST_ENTRY v11; // rdi
  RTL_SRWLOCK *v12; // rbx
  __int64 v13; // r14
  int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // r8
  __int64 v18; // [rsp+40h] [rbp-89h] BYREF
  struct _SLIST_ENTRY *v19; // [rsp+48h] [rbp-81h] BYREF
  __int64 v20; // [rsp+50h] [rbp-79h] BYREF
  __int64 v21; // [rsp+58h] [rbp-71h] BYREF
  __int64 v22; // [rsp+60h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v24; // [rsp+80h] [rbp-49h]
  __int64 v25; // [rsp+88h] [rbp-41h]
  __int64 *v26; // [rsp+90h] [rbp-39h]
  __int64 v27; // [rsp+98h] [rbp-31h]
  __int64 *v28; // [rsp+A0h] [rbp-29h]
  __int64 v29; // [rsp+A8h] [rbp-21h]
  __int64 *v30; // [rsp+B0h] [rbp-19h]
  __int64 v31; // [rsp+B8h] [rbp-11h]
  __int64 *v32; // [rsp+C0h] [rbp-9h]
  __int64 v33; // [rsp+C8h] [rbp-1h]

  LODWORD(v3) = 0;
  v4 = a2;
  *a3 = 0;
  v19 = 0;
  v6 = a1;
  if ( a1 != 0x1000000010000LL )
  {
    ApiObject = 1306;
    goto LABEL_3;
  }
  if ( a2 )
  {
    ApiObject = 87;
LABEL_3:
    if ( (Microsoft_Windows_WebIOEnableBits & 2) != 0 )
      McTemplateU0pxxxq_EventWriteTransfer(a1, (unsigned int)ApiInitializeFailedTrace, v3, *a3, v6, v4, ApiObject);
    return ApiObject;
  }
  ApiObject = WapCreateApiObject((__int64 *)&v19);
  if ( ApiObject )
  {
    LODWORD(v3) = (_DWORD)v19;
    goto LABEL_3;
  }
  CurrentProcessorNumber = (unsigned __int8)RtlGetCurrentProcessorNumber();
  v9 = (union _SLIST_HEADER *)((char *)WaHandleTable + 64 * CurrentProcessorNumber);
  while ( 1 )
  {
    v10 = InterlockedPopEntrySList(v9 + 2);
    v11 = v10;
    if ( v10 )
      break;
    ApiObject = WapExpandHandleTable((unsigned int)CurrentProcessorNumber);
    if ( ApiObject )
    {
      v3 = (__int64)v19;
      WaDereferenceApiObject(v19);
      WapDestroyApiObject(v3);
      goto LABEL_3;
    }
  }
  v12 = (RTL_SRWLOCK *)&v10[1];
  AcquireSRWLockExclusive((PSRWLOCK)&v10[1]);
  v13 = (__int64)v19;
  v14 = (*((_DWORD *)&v11[1].Next + 2) + 1) & 0xFFFFFFF;
  v11->Next = v19;
  *((_DWORD *)&v11[1].Next + 2) = v14 | 0x10000000;
  v15 = *((_QWORD *)&v11[1].Next + 1);
  ReleaseSRWLockExclusive(v12);
  *a3 = v15;
  if ( (Microsoft_Windows_WebIOEnableBits & 1) != 0 )
  {
    v22 = v4;
    LODWORD(v19) = 0;
    v21 = 0x1000000010000LL;
    v20 = v15;
    v24 = &v18;
    v18 = v13;
    v26 = &v20;
    v25 = 8;
    v28 = &v21;
    v30 = &v22;
    v32 = (__int64 *)&v19;
    v27 = 8;
    v29 = 8;
    v31 = 8;
    v33 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      (const EVENT_DESCRIPTOR *)ApiInitializeTrace,
      v16,
      6u,
      &v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18004e248  push    rbp
0x18004e24a  push    rbx
0x18004e24b  push    rsi
0x18004e24c  push    rdi
0x18004e24d  push    r12
0x18004e24f  push    r13
0x18004e251  push    r14
0x18004e253  push    r15
0x18004e255  lea     rbp, [rsp-1Fh]
0x18004e25a  sub     rsp, 0E8h
0x18004e261  mov     rax, cs:__security_cookie
0x18004e268  xor     rax, rsp
0x18004e26b  mov     [rbp+57h+var_50], rax
0x18004e26f  xor     edi, edi
0x18004e271  mov     esi, edx
0x18004e273  mov     rax, 1000000010000h
0x18004e27d  mov     qword ptr [r8], 0
0x18004e284  mov     [rsp+120h+var_D8], rdi
0x18004e289  mov     r15, r8
0x18004e28c  mov     r12, rcx
0x18004e28f  cmp     rcx, rax
0x18004e292  jz      short loc_18004E2CB
0x18004e294  mov     ebx, 51Ah
0x18004e299  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 2
0x18004e2a0  jz      loc_18004E405
0x18004e2a6  mov     r9, [r15]
0x18004e2a9  lea     rdx, ApiInitializeFailedTrace
0x18004e2b0  mov     [rsp+120h+var_F0], ebx
0x18004e2b4  mov     r8, rdi
0x18004e2b7  mov     [rsp+120h+var_F8], rsi
0x18004e2bc  mov     [rsp+120h+var_100], r12
0x18004e2c1  call    McTemplateU0pxxxq_EventWriteTransfer
0x18004e2c6  jmp     loc_18004E405
0x18004e2cb  test    edx, edx
0x18004e2cd  jnz     loc_18004E45E
0x18004e2d3  lea     rcx, [rsp+120h+var_D8]
0x18004e2d8  call    WapCreateApiObject
0x18004e2dd  mov     ebx, eax
0x18004e2df  test    eax, eax
0x18004e2e1  jnz     loc_18004E454
0x18004e2e7  call    cs:__imp_RtlGetCurrentProcessorNumber
0x18004e2ee  nop     dword ptr [rax+rax+00h]
0x18004e2f3  movzx   r14d, al
0x18004e2f7  mov     r13d, r14d
0x18004e2fa  shl     r13, 6
0x18004e2fe  add     r13, cs:WaHandleTable
0x18004e305  lea     rcx, [r13+20h]; ListHead
0x18004e309  call    cs:__imp_InterlockedPopEntrySList
0x18004e310  nop     dword ptr [rax+rax+00h]
0x18004e315  mov     rdi, rax
0x18004e318  test    rax, rax
0x18004e31b  jz      loc_18004E428
0x18004e321  lea     rbx, [rax+10h]
0x18004e325  mov     rcx, rbx; SRWLock
0x18004e328  call    cs:__imp_AcquireSRWLockExclusive
0x18004e32f  nop     dword ptr [rax+rax+00h]
0x18004e334  mov     eax, [rdi+18h]
0x18004e337  mov     rcx, rbx; SRWLock
0x18004e33a  mov     r14, [rsp+120h+var_D8]
0x18004e33f  inc     eax
0x18004e341  and     eax, 0FFFFFFFh
0x18004e346  mov     [rdi], r14
0x18004e349  bts     eax, 1Ch
0x18004e34d  mov     [rdi+18h], eax
0x18004e350  mov     rdi, [rdi+18h]
0x18004e354  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e35b  nop     dword ptr [rax+rax+00h]
0x18004e360  mov     [r15], rdi
0x18004e363  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 1
0x18004e36a  jz      loc_18004E403
0x18004e370  xor     edx, edx
0x18004e372  mov     [rbp+57h+var_C0], rsi
0x18004e376  mov     rax, 1000000010000h
0x18004e380  mov     dword ptr [rsp+120h+var_D8], edx
0x18004e384  mov     [rbp+57h+var_C8], rax
0x18004e388  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18004e38f  lea     rax, [rsp+120h+var_E0]
0x18004e394  mov     [rbp+57h+var_D0], rdi
0x18004e398  mov     [rbp+57h+var_A0], rax
0x18004e39c  lea     r9d, [rdx+6]
0x18004e3a0  lea     rax, [rbp+57h+var_D0]
0x18004e3a4  mov     [rsp+120h+var_E0], r14
0x18004e3a9  mov     [rbp+57h+var_90], rax
0x18004e3ad  lea     rdx, ApiInitializeTrace
0x18004e3b4  lea     rax, [rbp+57h+var_C8]
0x18004e3b8  mov     [rbp+57h+var_98], 8
0x18004e3c0  mov     [rbp+57h+var_80], rax
0x18004e3c4  lea     rax, [rbp+57h+var_C0]
0x18004e3c8  mov     [rbp+57h+var_70], rax
0x18004e3cc  lea     rax, [rsp+120h+var_D8]
0x18004e3d1  mov     [rbp+57h+var_60], rax
0x18004e3d5  lea     rax, [rbp+57h+var_B0]
0x18004e3d9  mov     [rsp+120h+var_100], rax
0x18004e3de  mov     [rbp+57h+var_88], 8
0x18004e3e6  mov     [rbp+57h+var_78], 8
0x18004e3ee  mov     [rbp+57h+var_68], 8
0x18004e3f6  mov     [rbp+57h+var_58], 4
0x18004e3fe  call    McGenEventWrite_EventWriteTransfer
0x18004e403  xor     ebx, ebx
0x18004e405  mov     eax, ebx
0x18004e407  mov     rcx, [rbp+57h+var_50]
0x18004e40b  xor     rcx, rsp; StackCookie
0x18004e40e  call    __security_check_cookie
0x18004e413  add     rsp, 0E8h
0x18004e41a  pop     r15
0x18004e41c  pop     r14
0x18004e41e  pop     r13
0x18004e420  pop     r12
0x18004e422  pop     rdi
0x18004e423  pop     rsi
0x18004e424  pop     rbx
0x18004e425  pop     rbp
0x18004e426  retn
0x18004e428  mov     ecx, r14d
0x18004e42b  call    WapExpandHandleTable
0x18004e430  mov     ebx, eax
0x18004e432  test    eax, eax
0x18004e434  jz      loc_18004E305
0x18004e43a  mov     rdi, [rsp+120h+var_D8]
0x18004e43f  mov     rcx, rdi
0x18004e442  call    WaDereferenceApiObject
0x18004e447  mov     rcx, rdi
0x18004e44a  call    WapDestroyApiObject
0x18004e44f  jmp     loc_18004E299
0x18004e454  mov     rdi, [rsp+120h+var_D8]
0x18004e459  jmp     loc_18004E299
0x18004e45e  mov     ebx, 57h ; 'W'
0x18004e463  jmp     loc_18004E299
```
