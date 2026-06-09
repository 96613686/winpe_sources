# SkMinidumpWriteDump

- ea: `0x1400bd2a0`
- end: `0x1400bd6c8`
- name: `SkMinidumpWriteDump`
- size: `1064`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x140014dd0`
- `0x1400961bc`

## callees

- `0x140001008`
- `0x140001040`
- `0x140002900`
- `0x14000b084`
- `0x14000f0f0`
- `0x140037e68`
- `0x140095cd8`
- `0x1400b1e8c`
- `0x1400bd2a0`
- `0x1400bd6d0`
- `0x1400bd738`
- `0x1400bd7c0`
- `0x1400bd910`
- `0x1400bde44`
- `0x1400be0b8`
- `0x1400be21c`
- `0x1400be4f8`
- `0x1400bf744`
- `0x1400bf8e4`
- `0x1400ef5e0`
- `0x1400f9a80`

## import_xrefs

- `cng!BCryptDestroyKey` at `0x1400bd617`
- `cng!BCryptDestroyKey` at `0x1400bd617`

## pseudocode

```c
__int64 __fastcall SkMinidumpWriteDump(int *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  __int64 v5; // rdi
  void *v6; // r12
  __int64 v7; // rsi
  _QWORD *StackBase; // rcx
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ebx
  void *v16; // r14
  __int64 v17; // r13
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  void *Pool; // rax
  int v22; // eax
  size_t v23; // r15
  void *v24; // rax
  int v25; // r9d
  __int64 v26; // r8
  __int64 v27; // r9
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  char v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h]
  __int64 v39[10]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v40[160]; // [rsp+D0h] [rbp-30h] BYREF
  size_t Size; // [rsp+170h] [rbp+70h]
  int v42; // [rsp+19Ch] [rbp+9Ch]

  v3 = a3;
  v32 = a3;
  v36 = a2;
  memset_0(v40, 0, 0xF0u);
  v34 = 0;
  hKey = 0;
  v5 = 0;
  v6 = 0;
  v35 = 0;
  v7 = 0;
  if ( !v3 )
  {
    v3 = *((_QWORD *)KeGetPcr()->NtTib.StackBase + 9);
    v32 = v3;
  }
  StackBase = KeGetPcr()->NtTib.StackBase;
  v9 = *(_QWORD *)(v3 + 48);
  v38 = v9;
  if ( StackBase )
  {
    v10 = StackBase[18];
    if ( v10 )
      --*(_WORD *)(v10 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(&qword_140148460);
  v33 = SkSuspendProcess(v9);
  if ( v33 )
  {
    v16 = (void *)SkpAlpcConnectWerPort();
    if ( !v16 )
    {
      if ( !a1 )
        goto LABEL_10;
      v15 = SkpSendErrorMessage(a1);
      if ( v15 < 0 )
        goto LABEL_11;
      v16 = (void *)SkpAlpcConnectWerPort();
      if ( !v16 )
      {
LABEL_10:
        v15 = -1073741772;
        goto LABEL_11;
      }
    }
    if ( !(unsigned __int8)SkpsIsProcessDumpEnabled(v3) )
    {
      v15 = -1073741637;
      goto LABEL_11;
    }
    Pool = (void *)SkAllocatePool(1, 0xC58u);
    v7 = (__int64)Pool;
    if ( !Pool )
    {
      v15 = -1073741670;
      goto LABEL_11;
    }
    memset_0(Pool, 0, 0xC58u);
    if ( a1 )
    {
      v34 = *a1;
      *(_DWORD *)(v7 + 16) = v34;
    }
    v22 = SkpPrepareEncryptionForCrash(v3, v7 + 1064, &hKey, &v35);
    v12 = 0x80000000LL;
    v15 = v22;
    if ( (int)(v22 + 0x80000000) >= 0 && v22 != -1073741275 )
    {
LABEL_27:
      v5 = v35;
      goto LABEL_11;
    }
    LOBYTE(v11) = a1 != 0;
    v42 = 8;
    v15 = SkpCalculateStreamInfo(v3, v11, v40);
    if ( v15 < 0 )
    {
      v17 = v32;
    }
    else
    {
      v23 = Size;
      v24 = (void *)SkAllocatePool(1, Size);
      v6 = v24;
      if ( !v24 )
      {
        v15 = -1073741670;
        goto LABEL_27;
      }
      memset_0(v24, 0, v23);
      v25 = (int)a1;
      v17 = v32;
      v15 = SkpWriteDumpData((_DWORD)v6, (unsigned int)v40, v32, v25, v36, v7);
      if ( v15 >= 0 )
      {
        v5 = v35;
        if ( v35 )
        {
          v15 = SkEncryptPage(v35, -1, v6, v23, 0, 0, v6, 1);
          if ( v15 < 0 )
            goto LABEL_12;
          *(_OWORD *)(v7 + 3140) = *(_OWORD *)(v5 + 56);
        }
        SkpAlpcSendReceiveWer(v16, v23, v6, v7);
        goto LABEL_12;
      }
    }
    v5 = v35;
    goto LABEL_12;
  }
  v15 = -1073741823;
  v16 = 0;
LABEL_11:
  v17 = v32;
LABEL_12:
  if ( (unsigned int)dword_140141980 > 5 && (unsigned __int8)tlgKeywordOn(v12, v11, v13, v14) )
  {
    v39[4] = (__int64)&v34;
    v36 = *(_QWORD *)(v17 + 432);
    v39[6] = (__int64)&v36;
    v39[8] = (__int64)&v32;
    v39[5] = 4;
    v39[7] = 8;
    LODWORD(v32) = v15;
    v39[9] = 4;
    tlgWriteTransfer_SkEtwWriteTransfer(v18, (int)&byte_1401186F1, v19, v20, 5u, (__int64)v39);
  }
  if ( v7 )
    SkFreePool(1, v7);
  if ( v6 )
    SkFreePool(1, v6);
  if ( v16 )
    ZwClose(v16);
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v5 )
  {
    SkFinalizePageEncryption(v5);
    SkFreePool(1, v5);
  }
  if ( v33 )
    SkResumeProcess(v38);
  RtlReleaseSRWLockExclusive(&qword_140148460);
  v28 = KeGetPcr()->NtTib.StackBase;
  if ( v28 )
  {
    v29 = v28[18];
    if ( v29 )
    {
      if ( (*(_WORD *)(v29 + xmmword_140167150))++ == 0xFFFF
        && *(_QWORD *)(v29 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v28[17]
        && !*(_WORD *)(v29 + *((_QWORD *)&xmmword_140167150 + 1)) )
      {
        SkiCheckForKernelApcDelivery(xmmword_140167160, v29, v26, v27);
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400bd2a0  mov     [rsp-8+arg_18], rbx
0x1400bd2a5  push    rbp
0x1400bd2a6  push    rsi
0x1400bd2a7  push    rdi
0x1400bd2a8  push    r12
0x1400bd2aa  push    r13
0x1400bd2ac  push    r14
0x1400bd2ae  push    r15
0x1400bd2b0  lea     rbp, [rsp-0C0h]
0x1400bd2b8  sub     rsp, 1C0h
0x1400bd2bf  mov     r15, r8
0x1400bd2c2  mov     [rsp+1F0h+var_1A8], r8
0x1400bd2c7  mov     [rsp+1F0h+var_190], rdx
0x1400bd2cc  mov     r13, rcx
0x1400bd2cf  xor     edx, edx; Val
0x1400bd2d1  lea     rcx, [rbp+0F0h+var_120]; void *
0x1400bd2d5  mov     r8d, 0F0h; Size
0x1400bd2db  call    memset_0
0x1400bd2e0  test    r13, r13
0x1400bd2e3  mov     [rsp+1F0h+var_19C], 0
0x1400bd2eb  mov     [rsp+1F0h+hKey], 0
0x1400bd2f4  setnz   [rsp+1F0h+var_1B0]
0x1400bd2f9  xor     edi, edi
0x1400bd2fb  xor     r12d, r12d
0x1400bd2fe  mov     [rsp+1F0h+var_198], rdi
0x1400bd303  xor     esi, esi
0x1400bd305  test    r15, r15
0x1400bd308  jnz     short loc_1400BD31C
0x1400bd30a  mov     rax, gs:8
0x1400bd313  mov     r15, [rax+48h]
0x1400bd317  mov     [rsp+1F0h+var_1A8], r15
0x1400bd31c  mov     rcx, gs:8
0x1400bd325  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400bd329  mov     rbx, [r15+30h]
0x1400bd32d  mov     [rsp+1F0h+var_180], rbx
0x1400bd332  test    rcx, rcx
0x1400bd335  jz      short loc_1400BD34F
0x1400bd337  mov     rcx, [rcx+90h]
0x1400bd33e  test    rcx, rcx
0x1400bd341  jz      short loc_1400BD34F
0x1400bd343  mov     rax, qword ptr cs:xmmword_140167150
0x1400bd34a  add     [rcx+rax], dx
0x1400bd34e  nop
0x1400bd34f  lea     rcx, qword_140148460
0x1400bd356  call    SkAcquirePushLockExclusive
0x1400bd35b  mov     rcx, rbx
0x1400bd35e  call    SkSuspendProcess
0x1400bd363  mov     [rsp+1F0h+var_1A0], al
0x1400bd367  test    al, al
0x1400bd369  jnz     short loc_1400BD378
0x1400bd36b  xor     r15d, r15d
0x1400bd36e  mov     ebx, 0C0000001h
0x1400bd373  mov     r14d, r15d
0x1400bd376  jmp     short loc_1400BD39A
0x1400bd378  call    SkpAlpcConnectWerPort
0x1400bd37d  mov     r14, rax
0x1400bd380  test    rax, rax
0x1400bd383  jnz     loc_1400BD45B
0x1400bd389  test    r13, r13
0x1400bd38c  jnz     loc_1400BD438
0x1400bd392  mov     ebx, 0C0000034h
0x1400bd397  xor     r15d, r15d
0x1400bd39a  mov     r13, [rsp+1F0h+var_1A8]
0x1400bd39f  mov     eax, cs:dword_140141980
0x1400bd3a5  cmp     eax, 5
0x1400bd3a8  jbe     short loc_1400BD41B
0x1400bd3aa  call    _tlgKeywordOn
0x1400bd3af  test    al, al
0x1400bd3b1  jz      short loc_1400BD41B
0x1400bd3b3  mov     eax, [rsp+1F0h+var_19C]
0x1400bd3b7  lea     rdx, byte_1401186F1; int
0x1400bd3be  mov     [rsp+1F0h+var_19C], eax
0x1400bd3c2  lea     rax, [rsp+1F0h+var_19C]
0x1400bd3c7  mov     [rbp+0F0h+var_150], rax
0x1400bd3cb  mov     rax, [r13+1B0h]
0x1400bd3d2  mov     [rsp+1F0h+var_190], rax
0x1400bd3d7  lea     rax, [rsp+1F0h+var_190]
0x1400bd3dc  mov     [rbp+0F0h+var_140], rax
0x1400bd3e0  lea     rax, [rsp+1F0h+var_1A8]
0x1400bd3e5  mov     [rbp+0F0h+var_130], rax
0x1400bd3e9  lea     rax, [rbp+0F0h+var_170]
0x1400bd3ed  mov     [rsp+1F0h+var_1C8], rax; __int64
0x1400bd3f2  mov     [rsp+1F0h+var_1D0], 5; ULONG
0x1400bd3fa  mov     [rbp+0F0h+var_148], 4
0x1400bd402  mov     [rbp+0F0h+var_138], 8
0x1400bd40a  mov     dword ptr [rsp+1F0h+var_1A8], ebx
0x1400bd40e  mov     [rbp+0F0h+var_128], 4
0x1400bd416  call    _tlgWriteTransfer_SkEtwWriteTransfer
0x1400bd41b  test    rsi, rsi
0x1400bd41e  jz      loc_1400BD5EC
0x1400bd424  mov     rdx, rsi
0x1400bd427  mov     esi, 1
0x1400bd42c  mov     ecx, esi
0x1400bd42e  call    SkFreePool
0x1400bd433  jmp     loc_1400BD5F1
0x1400bd438  mov     rcx, r13
0x1400bd43b  call    SkpSendErrorMessage
0x1400bd440  mov     ebx, eax
0x1400bd442  test    eax, eax
0x1400bd444  js      loc_1400BD397
0x1400bd44a  call    SkpAlpcConnectWerPort
0x1400bd44f  mov     r14, rax
0x1400bd452  test    rax, rax
0x1400bd455  jz      loc_1400BD392
0x1400bd45b  mov     rcx, r15
0x1400bd45e  call    SkpsIsProcessDumpEnabled
0x1400bd463  test    al, al
0x1400bd465  jnz     short loc_1400BD471
0x1400bd467  mov     ebx, 0C00000BBh
0x1400bd46c  jmp     loc_1400BD397
0x1400bd471  mov     ebx, 0C58h
0x1400bd476  mov     r8d, 20726557h
0x1400bd47c  mov     edx, ebx
0x1400bd47e  mov     ecx, 1
0x1400bd483  call    SkAllocatePool
0x1400bd488  mov     rsi, rax
0x1400bd48b  test    rax, rax
0x1400bd48e  jnz     short loc_1400BD49A
0x1400bd490  mov     ebx, 0C000009Ah
0x1400bd495  jmp     loc_1400BD397
0x1400bd49a  mov     r8, rbx; Size
0x1400bd49d  xor     edx, edx; Val
0x1400bd49f  mov     rcx, rsi; void *
0x1400bd4a2  call    memset_0
0x1400bd4a7  test    r13, r13
0x1400bd4aa  jz      short loc_1400BD4B7
0x1400bd4ac  mov     eax, [r13+0]
0x1400bd4b0  mov     [rsp+1F0h+var_19C], eax
0x1400bd4b4  mov     [rsi+10h], eax
0x1400bd4b7  lea     rdx, [rsi+428h]
0x1400bd4be  mov     rcx, r15
0x1400bd4c1  lea     r9, [rsp+1F0h+var_198]
0x1400bd4c6  lea     r8, [rsp+1F0h+hKey]
0x1400bd4cb  call    SkpPrepareEncryptionForCrash
0x1400bd4d0  mov     ecx, 80000000h
0x1400bd4d5  mov     ebx, eax
0x1400bd4d7  add     eax, ecx
0x1400bd4d9  test    ecx, eax
0x1400bd4db  jnz     short loc_1400BD4EF
0x1400bd4dd  cmp     ebx, 0C0000225h
0x1400bd4e3  jz      short loc_1400BD4EF
0x1400bd4e5  mov     rdi, [rsp+1F0h+var_198]
0x1400bd4ea  jmp     loc_1400BD397
0x1400bd4ef  mov     dl, [rsp+1F0h+var_1B0]
0x1400bd4f3  lea     r8, [rbp+0F0h+var_120]
0x1400bd4f7  mov     rcx, r15
0x1400bd4fa  mov     [rbp+0F0h+var_54], 8
0x1400bd504  call    SkpCalculateStreamInfo
0x1400bd509  xor     r15d, r15d
0x1400bd50c  mov     ebx, eax
0x1400bd50e  test    eax, eax
0x1400bd510  js      loc_1400BD5D8
0x1400bd516  mov     r15, [rbp+0F0h+Size]
0x1400bd51a  mov     r8d, 20726557h
0x1400bd520  mov     rdx, r15
0x1400bd523  mov     ecx, 1
0x1400bd528  call    SkAllocatePool
0x1400bd52d  mov     r12, rax
0x1400bd530  test    rax, rax
0x1400bd533  jnz     short loc_1400BD53C
0x1400bd535  mov     ebx, 0C000009Ah
0x1400bd53a  jmp     short loc_1400BD4E5
0x1400bd53c  mov     r8, r15; Size
0x1400bd53f  xor     edx, edx; Val
0x1400bd541  mov     rcx, r12; void *
0x1400bd544  call    memset_0
0x1400bd549  mov     rax, [rsp+1F0h+var_190]
0x1400bd54e  lea     rdx, [rbp+0F0h+var_120]
0x1400bd552  mov     r9, r13
0x1400bd555  mov     [rsp+1F0h+var_1C8], rsi
0x1400bd55a  mov     r13, [rsp+1F0h+var_1A8]
0x1400bd55f  mov     rcx, r12
0x1400bd562  mov     r8, r13
0x1400bd565  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x1400bd56a  call    SkpWriteDumpData
0x1400bd56f  mov     ebx, eax
0x1400bd571  test    eax, eax
0x1400bd573  js      short loc_1400BD5DF
0x1400bd575  mov     rdi, [rsp+1F0h+var_198]
0x1400bd57a  test    rdi, rdi
0x1400bd57d  jz      short loc_1400BD5BF
0x1400bd57f  mov     [rsp+1F0h+var_1B8], 1
0x1400bd584  mov     r9, r15
0x1400bd587  mov     [rsp+1F0h+var_1C0], r12
0x1400bd58c  mov     r8, r12
0x1400bd58f  mov     [rsp+1F0h+var_1C8], 0
0x1400bd598  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400bd59c  mov     rcx, rdi
0x1400bd59f  mov     qword ptr [rsp+1F0h+var_1D0], 0
0x1400bd5a8  call    SkEncryptPage
0x1400bd5ad  mov     ebx, eax
0x1400bd5af  test    eax, eax
0x1400bd5b1  js      short loc_1400BD5D0
0x1400bd5b3  movups  xmm0, xmmword ptr [rdi+38h]
0x1400bd5b7  movdqu  xmmword ptr [rsi+0C44h], xmm0
0x1400bd5bf  mov     r9, rsi
0x1400bd5c2  mov     r8, r12
0x1400bd5c5  mov     rdx, r15
0x1400bd5c8  mov     rcx, r14
0x1400bd5cb  call    SkpAlpcSendReceiveWer
0x1400bd5d0  xor     r15d, r15d
0x1400bd5d3  jmp     loc_1400BD39F
0x1400bd5d8  mov     r13, [rsp+1F0h+var_1A8]
0x1400bd5dd  jmp     short loc_1400BD5E2
0x1400bd5df  xor     r15d, r15d
0x1400bd5e2  mov     rdi, [rsp+1F0h+var_198]
0x1400bd5e7  jmp     loc_1400BD39F
0x1400bd5ec  mov     esi, 1
0x1400bd5f1  test    r12, r12
0x1400bd5f4  jz      short loc_1400BD600
0x1400bd5f6  mov     rdx, r12
0x1400bd5f9  mov     ecx, esi
0x1400bd5fb  call    SkFreePool
0x1400bd600  test    r14, r14
0x1400bd603  jz      short loc_1400BD60D
0x1400bd605  mov     rcx, r14; Handle
0x1400bd608  call    ZwClose
0x1400bd60d  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1400bd612  test    rcx, rcx
0x1400bd615  jz      short loc_1400BD623
0x1400bd617  call    cs:__imp_BCryptDestroyKey
0x1400bd61e  nop     dword ptr [rax+rax+00h]
0x1400bd623  test    rdi, rdi
0x1400bd626  jz      short loc_1400BD63A
0x1400bd628  mov     rcx, rdi
0x1400bd62b  call    SkFinalizePageEncryption
0x1400bd630  mov     rdx, rdi
0x1400bd633  mov     ecx, esi
0x1400bd635  call    SkFreePool
0x1400bd63a  cmp     [rsp+1F0h+var_1A0], r15b
0x1400bd63f  jz      short loc_1400BD64B
0x1400bd641  mov     rcx, [rsp+1F0h+var_180]
0x1400bd646  call    SkResumeProcess
0x1400bd64b  lea     rcx, qword_140148460
0x1400bd652  call    RtlReleaseSRWLockExclusive
0x1400bd657  mov     rcx, gs:8
0x1400bd660  test    rcx, rcx
0x1400bd663  jz      short loc_1400BD6AA
0x1400bd665  mov     rdx, [rcx+90h]
0x1400bd66c  test    rdx, rdx
0x1400bd66f  jz      short loc_1400BD6AA
0x1400bd671  nop
0x1400bd672  mov     rax, qword ptr cs:xmmword_140167150
0x1400bd679  add     [rdx+rax], si
0x1400bd67d  jnz     short loc_1400BD6AA
0x1400bd67f  mov     rax, [rcx+88h]
0x1400bd686  nop
0x1400bd687  mov     rcx, qword ptr cs:xmmword_140167160
0x1400bd68e  add     rax, rcx
0x1400bd691  cmp     [rdx+rcx], rax
0x1400bd695  jz      short loc_1400BD6AA
0x1400bd697  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400bd69e  cmp     [rdx+rax], r15w
0x1400bd6a3  jnz     short loc_1400BD6AA
0x1400bd6a5  call    SkiCheckForKernelApcDelivery
0x1400bd6aa  mov     eax, ebx
0x1400bd6ac  mov     rbx, [rsp+1F0h+arg_18]
0x1400bd6b4  add     rsp, 1C0h
0x1400bd6bb  pop     r15
0x1400bd6bd  pop     r14
0x1400bd6bf  pop     r13
0x1400bd6c1  pop     r12
0x1400bd6c3  pop     rdi
0x1400bd6c4  pop     rsi
0x1400bd6c5  pop     rbp
0x1400bd6c6  retn
```
