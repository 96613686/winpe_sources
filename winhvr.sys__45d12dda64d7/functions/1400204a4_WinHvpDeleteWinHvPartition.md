# WinHvpDeleteWinHvPartition

- ea: `0x1400204a4`
- end: `0x140020783`
- name: `WinHvpDeleteWinHvPartition`
- size: `735`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14001f8b0`
- `0x14001fe90`
- `0x1400202cc`

## callees

- `0x140001008`
- `0x140001038`
- `0x1400024d0`
- `0x140009c50`
- `0x14000b008`
- `0x14000b040`
- `0x14001fea8`
- `0x1400204a4`
- `0x14002078c`

## import_xrefs

- `ntoskrnl!KeGenericCallDpc` at `0x14002073e`
- `ntoskrnl!KeGenericCallDpc` at `0x14002073e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400204cd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400204cd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400204e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400204e2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400205b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002071d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400205b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002071d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400205c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020729`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400205c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020729`

## string_xrefs

- `0x1400205f3`: `WinHvpDeleteWinHvPartition`

## pseudocode

```c
__int64 __fastcall WinHvpDeleteWinHvPartition(unsigned __int64 a1, char a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ecx
  int v8; // eax
  __int64 v9; // rbx
  __int16 v10; // di
  __int64 v11; // rdi
  __int64 v12; // rax
  int v13; // r14d
  __int64 v14; // rcx
  _DWORD *Pool; // rax
  _DWORD *v16; // rcx
  int v17; // r9d
  __int64 v18; // rdx
  int v19; // eax
  int v20; // r10d
  __int128 v21; // xmm0
  __int64 v22; // rax
  __int16 v24; // [rsp+30h] [rbp-49h] BYREF
  int v25; // [rsp+34h] [rbp-45h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+40h] [rbp-39h] BYREF
  const char *v28; // [rsp+60h] [rbp-19h]
  __int64 v29; // [rsp+68h] [rbp-11h]
  __int16 *v30; // [rsp+70h] [rbp-9h]
  __int64 v31; // [rsp+78h] [rbp-1h]
  int *v32; // [rsp+80h] [rbp+7h]
  __int64 v33; // [rsp+88h] [rbp+Fh]
  __int64 *v34; // [rsp+90h] [rbp+17h]
  __int64 v35; // [rsp+98h] [rbp+1Fh]

  v4 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&WinHvpPartitionArrayLock, 0);
  if ( WinHvpPartitionArray && (v6 = 0, v7 = *(_DWORD *)WinHvpPartitionArray - 1, v7 >= 0) )
  {
    while ( 1 )
    {
      v5 = (unsigned int)(v7 + v6) >> 1;
      if ( *(_QWORD *)(WinHvpPartitionArray + 16 * v5 + 8) == a1 )
        break;
      if ( *(_QWORD *)(WinHvpPartitionArray + 16LL * ((unsigned int)(v7 + v6) >> 1) + 8) >= a1 )
        v7 = v5 - 1;
      v8 = v5 + 1;
      if ( *(_QWORD *)(WinHvpPartitionArray + 16 * v5 + 8) >= a1 )
        v8 = v6;
      v6 = (unsigned int)v8;
      if ( v8 > v7 )
        goto LABEL_9;
    }
    v9 = *(_QWORD *)(WinHvpPartitionArray + 16LL * ((unsigned int)(v7 + v6) >> 1) + 16);
    if ( v9 )
      v4 = v5;
  }
  else
  {
LABEL_9:
    v9 = 0;
  }
  if ( a2 )
  {
    if ( !v9 )
    {
      LODWORD(v9) = -1070268403;
      v10 = 1728;
LABEL_24:
      ExReleasePushLockExclusiveEx(&WinHvpPartitionArrayLock, 0);
      KeLeaveCriticalRegion();
      if ( (int)v9 < 0 && (unsigned int)dword_140011000 > 2 && (unsigned __int8)tlgKeywordOn() )
      {
        v29 = 27;
        v28 = "WinHvpDeleteWinHvPartition";
        v24 = v10;
        v30 = &v24;
        v31 = 2;
        v32 = &v25;
        v25 = v9;
        v34 = (__int64 *)&v26;
        v33 = 4;
        v26 = a1;
        v35 = 8;
        tlgWriteTransfer_EtwWriteTransfer(v14, (unsigned __int8 *)byte_14000E8CB, 0, 0, 6u, &v27);
      }
      return (unsigned int)v9;
    }
    if ( *(_QWORD *)(v9 + 24) || *(_QWORD *)(v9 + 48) )
    {
      LODWORD(v9) = -1070268409;
      v10 = 1740;
      goto LABEL_24;
    }
    WinHvpAddUnlinkedPartitionId(a1, v5, v6);
  }
  else
  {
    WinHvpRemoveUnlinkedPartitionId(a1);
    if ( !v9 )
    {
      v10 = 1700;
      goto LABEL_24;
    }
  }
  v11 = WinHvpPartitionArray;
  v12 = *(int *)WinHvpPartitionArray;
  v13 = v12 - 1;
  if ( (_DWORD)v12 == 1 )
  {
    WinHvpPartitionArray = 0;
  }
  else
  {
    Pool = (_DWORD *)WinHvpAllocatePool(66, 16 * (v12 - 1) + 8, 1098270807);
    v16 = Pool;
    if ( Pool )
    {
      *Pool = v13;
      v17 = 0;
      v18 = WinHvpPartitionArray;
      v19 = 0;
      if ( *(int *)WinHvpPartitionArray > 0 )
      {
        do
        {
          v20 = v19 + 1;
          if ( v19 != v4 )
          {
            if ( *(_QWORD *)(v18 + 16LL * v19 + 16) )
            {
              v21 = *(_OWORD *)(v18 + 16LL * v19 + 8);
              v22 = 2LL * v17++;
              *(_OWORD *)&v16[2 * v22 + 2] = v21;
            }
            else
            {
              --*v16;
            }
          }
          v18 = WinHvpPartitionArray;
          v19 = v20;
        }
        while ( v20 < *(_DWORD *)WinHvpPartitionArray );
      }
      if ( !*v16 )
      {
        WinHvpFreePoolWithTag(v16, 1098270807);
        v16 = 0;
      }
      v11 = WinHvpPartitionArray;
      WinHvpPartitionArray = (__int64)v16;
    }
    else
    {
      v11 = 0;
      *(_QWORD *)(WinHvpPartitionArray + 16 * (v4 + 1LL)) = 0;
    }
  }
  ExReleasePushLockExclusiveEx(&WinHvpPartitionArrayLock, 0);
  KeLeaveCriticalRegion();
  KeGenericCallDpc(WinHvpSynchronizationDpc, 0);
  WinHvpDereferencePartition(v9);
  if ( v11 )
    WinHvpFreePoolWithTag(v11, 1098270807);
  LODWORD(v9) = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400204a4  push    rbp
0x1400204a6  push    rbx
0x1400204a7  push    rsi
0x1400204a8  push    rdi
0x1400204a9  push    r14
0x1400204ab  lea     rbp, [rsp-37h]
0x1400204b0  sub     rsp, 0B0h
0x1400204b7  mov     rax, cs:__security_cookie
0x1400204be  xor     rax, rsp
0x1400204c1  mov     [rbp+57h+var_30], rax
0x1400204c5  mov     dil, dl
0x1400204c8  mov     r14, rcx
0x1400204cb  xor     esi, esi
0x1400204cd  call    cs:__imp_KeEnterCriticalRegion
0x1400204d4  nop     dword ptr [rax+rax+00h]
0x1400204d9  xor     edx, edx
0x1400204db  lea     rcx, WinHvpPartitionArrayLock
0x1400204e2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400204e9  nop     dword ptr [rax+rax+00h]
0x1400204ee  mov     rbx, cs:WinHvpPartitionArray
0x1400204f5  test    rbx, rbx
0x1400204f8  jz      short loc_14002052A
0x1400204fa  mov     ecx, [rbx]
0x1400204fc  xor     r8d, r8d
0x1400204ff  sub     ecx, 1
0x140020502  js      short loc_14002052A
0x140020504  lea     eax, [rcx+r8]
0x140020508  shr     eax, 1
0x14002050a  mov     edx, eax
0x14002050c  add     rax, rax
0x14002050f  cmp     [rbx+rax*8+8], r14
0x140020514  jz      short loc_140020542
0x140020516  lea     eax, [rdx-1]
0x140020519  cmovnb  ecx, eax
0x14002051c  lea     eax, [rdx+1]
0x14002051f  cmovnb  eax, r8d
0x140020523  mov     r8d, eax
0x140020526  cmp     eax, ecx
0x140020528  jle     short loc_140020504
0x14002052a  xor     ebx, ebx
0x14002052c  test    dil, dil
0x14002052f  jz      short loc_14002059C
0x140020531  test    rbx, rbx
0x140020534  jnz     short loc_14002054F
0x140020536  mov     ebx, 0C035000Dh
0x14002053b  mov     edi, 6C0h
0x140020540  jmp     short loc_1400205AE
0x140020542  mov     rbx, [rbx+rax*8+10h]
0x140020547  test    rbx, rbx
0x14002054a  cmovnz  esi, edx
0x14002054d  jmp     short loc_14002052C
0x14002054f  mov     rax, [rbx+18h]
0x140020553  test    rax, rax
0x140020556  jnz     short loc_140020590
0x140020558  mov     rax, [rbx+30h]
0x14002055c  test    rax, rax
0x14002055f  jnz     short loc_140020590
0x140020561  mov     rcx, r14
0x140020564  call    WinHvpAddUnlinkedPartitionId
0x140020569  mov     rdi, cs:WinHvpPartitionArray
0x140020570  movsxd  rax, dword ptr [rdi]
0x140020573  lea     r14d, [rax-1]
0x140020577  test    r14d, r14d
0x14002057a  jnz     loc_140020669
0x140020580  mov     cs:WinHvpPartitionArray, 0
0x14002058b  jmp     loc_140020714
0x140020590  mov     ebx, 0C0350007h
0x140020595  mov     edi, 6CCh
0x14002059a  jmp     short loc_1400205AE
0x14002059c  mov     rcx, r14
0x14002059f  call    WinHvpRemoveUnlinkedPartitionId
0x1400205a4  test    rbx, rbx
0x1400205a7  jnz     short loc_140020569
0x1400205a9  mov     edi, 6A4h
0x1400205ae  xor     edx, edx
0x1400205b0  lea     rcx, WinHvpPartitionArrayLock
0x1400205b7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400205be  nop     dword ptr [rax+rax+00h]
0x1400205c3  call    cs:__imp_KeLeaveCriticalRegion
0x1400205ca  nop     dword ptr [rax+rax+00h]
0x1400205cf  test    ebx, ebx
0x1400205d1  jns     loc_140020766
0x1400205d7  mov     eax, cs:dword_140011000
0x1400205dd  cmp     eax, 2
0x1400205e0  jbe     loc_140020766
0x1400205e6  call    _tlgKeywordOn
0x1400205eb  test    al, al
0x1400205ed  jz      loc_140020766
0x1400205f3  lea     rax, aWinhvpdeletewi; "WinHvpDeleteWinHvPartition"
0x1400205fa  mov     [rbp+57h+var_68], 1Bh
0x140020602  mov     [rbp+57h+var_70], rax
0x140020606  lea     rdx, byte_14000E8CB
0x14002060d  lea     rax, [rbp+57h+var_A0]
0x140020611  mov     [rbp+57h+var_A0], di
0x140020615  mov     [rbp+57h+var_60], rax
0x140020619  xor     r9d, r9d
0x14002061c  lea     rax, [rbp+57h+var_9C]
0x140020620  mov     [rbp+57h+var_58], 2
0x140020628  mov     [rbp+57h+var_50], rax
0x14002062c  xor     r8d, r8d
0x14002062f  lea     rax, [rbp+57h+var_98]
0x140020633  mov     [rbp+57h+var_9C], ebx
0x140020636  mov     [rbp+57h+var_40], rax
0x14002063a  lea     rax, [rbp+57h+var_90]
0x14002063e  mov     [rsp+0D0h+var_A8], rax
0x140020643  mov     [rsp+0D0h+var_B0], 6
0x14002064b  mov     [rbp+57h+var_48], 4
0x140020653  mov     [rbp+57h+var_98], r14
0x140020657  mov     [rbp+57h+var_38], 8
0x14002065f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140020664  jmp     loc_140020766
0x140020669  lea     rdx, [rax-1]
0x14002066d  mov     ecx, 42h ; 'B'
0x140020672  shl     rdx, 4
0x140020676  mov     r8d, 41764857h
0x14002067c  add     rdx, 8
0x140020680  call    WinHvpAllocatePool
0x140020685  mov     rcx, rax
0x140020688  test    rax, rax
0x14002068b  jz      short loc_1400206FF
0x14002068d  mov     [rax], r14d
0x140020690  xor     r9d, r9d
0x140020693  mov     rdx, cs:WinHvpPartitionArray
0x14002069a  xor     eax, eax
0x14002069c  cmp     [rdx], eax
0x14002069e  jle     short loc_1400206DE
0x1400206a0  lea     r10d, [rax+1]
0x1400206a4  cmp     eax, esi
0x1400206a6  jz      short loc_1400206CF
0x1400206a8  movsxd  r8, eax
0x1400206ab  add     r8, r8
0x1400206ae  cmp     qword ptr [rdx+r8*8+10h], 0
0x1400206b4  jnz     short loc_1400206BA
0x1400206b6  dec     dword ptr [rcx]
0x1400206b8  jmp     short loc_1400206CF
0x1400206ba  movups  xmm0, xmmword ptr [rdx+r8*8+8]
0x1400206c0  movsxd  rax, r9d
0x1400206c3  add     rax, rax
0x1400206c6  inc     r9d
0x1400206c9  movdqu  xmmword ptr [rcx+rax*8+8], xmm0
0x1400206cf  mov     rdx, cs:WinHvpPartitionArray
0x1400206d6  mov     eax, r10d
0x1400206d9  cmp     r10d, [rdx]
0x1400206dc  jl      short loc_1400206A0
0x1400206de  cmp     dword ptr [rcx], 0
0x1400206e1  jnz     short loc_1400206EF
0x1400206e3  mov     edx, 41764857h
0x1400206e8  call    WinHvpFreePoolWithTag
0x1400206ed  xor     ecx, ecx
0x1400206ef  mov     rdi, cs:WinHvpPartitionArray
0x1400206f6  mov     cs:WinHvpPartitionArray, rcx
0x1400206fd  jmp     short loc_140020714
0x1400206ff  mov     rax, cs:WinHvpPartitionArray
0x140020706  xor     edi, edi
0x140020708  mov     edx, esi
0x14002070a  inc     rdx
0x14002070d  add     rdx, rdx
0x140020710  mov     [rax+rdx*8], rdi
0x140020714  xor     edx, edx
0x140020716  lea     rcx, WinHvpPartitionArrayLock
0x14002071d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140020724  nop     dword ptr [rax+rax+00h]
0x140020729  call    cs:__imp_KeLeaveCriticalRegion
0x140020730  nop     dword ptr [rax+rax+00h]
0x140020735  xor     edx, edx
0x140020737  lea     rcx, WinHvpSynchronizationDpc
0x14002073e  call    cs:__imp_KeGenericCallDpc
0x140020745  nop     dword ptr [rax+rax+00h]
0x14002074a  mov     rcx, rbx
0x14002074d  call    WinHvpDereferencePartition
0x140020752  test    rdi, rdi
0x140020755  jz      short loc_140020764
0x140020757  mov     edx, 41764857h
0x14002075c  mov     rcx, rdi
0x14002075f  call    WinHvpFreePoolWithTag
0x140020764  xor     ebx, ebx
0x140020766  mov     eax, ebx
0x140020768  mov     rcx, [rbp+57h+var_30]
0x14002076c  xor     rcx, rsp; StackCookie
0x14002076f  call    __security_check_cookie
0x140020774  add     rsp, 0B0h
0x14002077b  pop     r14
0x14002077d  pop     rdi
0x14002077e  pop     rsi
0x14002077f  pop     rbx
0x140020780  pop     rbp
0x140020781  retn
```
