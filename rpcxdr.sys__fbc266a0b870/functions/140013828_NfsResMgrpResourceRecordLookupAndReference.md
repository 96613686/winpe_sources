# NfsResMgrpResourceRecordLookupAndReference

- ea: `0x140013828`
- end: `0x140013900`
- name: `NfsResMgrpResourceRecordLookupAndReference`
- size: `216`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400128ac`
- `0x1400129c4`
- `0x140013044`
- `0x14001318c`
- `0x140013908`
- `0x1400139e4`
- `0x140013af8`

## callees

- `0x1400122e0`
- `0x140013828`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001386b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001386b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400138d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400138d4`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14001388c`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14001388c`

## pseudocode

```c
__int64 __fastcall NfsResMgrpResourceRecordLookupAndReference(int a1, _QWORD *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rbx
  int v5; // edi
  unsigned int v6; // edx
  __int64 result; // rax
  _BYTE LockHandle[32]; // [rsp+20h] [rbp-58h] BYREF
  __int128 Buffer; // [rsp+40h] [rbp-38h] BYREF
  __int128 v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-18h]

  v10 = 0;
  Buffer = 0;
  v11 = 0;
  DWORD2(v10) = a1;
  memset(LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)NfsResMgrpRoot + 3, (PKLOCK_QUEUE_HANDLE)LockHandle);
  LockHandle[24] = 1;
  v3 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)NfsResMgrpRoot + 48), &Buffer);
  if ( v3 )
  {
    v4 = v3[4];
    v5 = 0;
    v6 = _InterlockedIncrement((volatile signed __int32 *)(v4 + 4));
    if ( NfsRefHistoryTracingpGlobal )
      NfsReferenceHistoryCaptureRecord((_DWORD *)v4, v6, 0);
  }
  else
  {
    v4 = 0;
    v5 = -1068285916;
  }
  LockHandle[24] = 0;
  KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
  result = (unsigned int)v5;
  if ( v5 < 0 )
    v4 = 0;
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x140013828  mov     r11, rsp
0x14001382b  mov     [r11+8], rbx
0x14001382f  mov     [r11+10h], rsi
0x140013833  push    rdi
0x140013834  sub     rsp, 70h
0x140013838  xorps   xmm0, xmm0
0x14001383b  xor     eax, eax
0x14001383d  movups  [rsp+78h+var_28], xmm0
0x140013842  mov     rsi, rdx
0x140013845  lea     rdx, [r11-58h]; LockHandle
0x140013849  movups  [rsp+78h+Buffer], xmm0
0x14001384e  mov     [r11-18h], rax
0x140013852  mov     dword ptr [rsp+78h+var_28+8], ecx
0x140013856  mov     rcx, cs:NfsResMgrpRoot
0x14001385d  add     rcx, 18h; SpinLock
0x140013861  movups  xmmword ptr [rsp+78h+LockHandle], xmm0
0x140013866  movups  xmmword ptr [rsp+78h+LockHandle+10h], xmm0
0x14001386b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013872  nop     dword ptr [rax+rax+00h]
0x140013877  mov     rcx, cs:NfsResMgrpRoot
0x14001387e  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140013883  add     rcx, 30h ; '0'; Table
0x140013887  mov     [rsp+78h+LockHandle+18h], 1
0x14001388c  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140013893  nop     dword ptr [rax+rax+00h]
0x140013898  test    rax, rax
0x14001389b  jz      short loc_1400138C3
0x14001389d  mov     rbx, [rax+20h]
0x1400138a1  xor     edi, edi
0x1400138a3  lea     edx, [rdi+1]
0x1400138a6  lock xadd [rbx+4], edx
0x1400138ab  inc     edx
0x1400138ad  cmp     cs:NfsRefHistoryTracingpGlobal, rdi
0x1400138b4  jz      short loc_1400138CA
0x1400138b6  xor     r8d, r8d
0x1400138b9  mov     rcx, rbx
0x1400138bc  call    NfsReferenceHistoryCaptureRecord
0x1400138c1  jmp     short loc_1400138CA
0x1400138c3  xor     ebx, ebx
0x1400138c5  mov     edi, 0C0534024h
0x1400138ca  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400138cf  mov     [rsp+78h+LockHandle+18h], 0
0x1400138d4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400138db  nop     dword ptr [rax+rax+00h]
0x1400138e0  xor     ecx, ecx
0x1400138e2  lea     r11, [rsp+78h+var_8]
0x1400138e7  test    edi, edi
0x1400138e9  mov     eax, edi
0x1400138eb  cmovs   rbx, rcx
0x1400138ef  mov     [rsi], rbx
0x1400138f2  mov     rbx, [r11+10h]
0x1400138f6  mov     rsi, [r11+18h]
0x1400138fa  mov     rsp, r11
0x1400138fd  pop     rdi
0x1400138fe  retn
```
