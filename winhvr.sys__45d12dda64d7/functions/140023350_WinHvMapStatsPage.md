# WinHvMapStatsPage

- ea: `0x140023350`
- end: `0x140023532`
- name: `WinHvMapStatsPage`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140005dcc`
- `0x140007620`
- `0x140009c50`
- `0x14000b008`
- `0x14000b040`
- `0x140023350`
- `0x1400236fc`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400234f1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400234f1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400233e2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400233e2`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x140023421`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x140023421`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400234de`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400234de`
- `ntoskrnl!MmMapIoSpaceEx` at `0x14002348f`
- `ntoskrnl!MmMapIoSpaceEx` at `0x14002348f`

## pseudocode

```c
__int64 __fastcall WinHvMapStatsPage(unsigned int a1, _OWORD *a2, __int64 *a3, __int64 *a4)
{
  char v4; // r14
  __int64 Pool; // rsi
  int v11; // edi
  _DWORD *inserted; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int8 NewElement[8]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v18; // [rsp+28h] [rbp-48h] BYREF
  _OWORD Buffer[3]; // [rsp+30h] [rbp-40h] BYREF

  v4 = 0;
  v18 = -1;
  *a3 = 0;
  *a4 = 0;
  NewElement[0] = 0;
  memset(Buffer, 0, 44);
  if ( !WinHvpConnected )
    return 3224698882LL;
  Pool = WinHvpAllocatePool(258, 8, 1333151831);
  if ( Pool )
  {
    ExAcquireFastMutex(&WinHvpStatsTableLock);
    memset(Buffer, 0, sizeof(Buffer));
    LODWORD(Buffer[0]) = a1;
    LODWORD(Buffer[2]) = 0;
    *(_OWORD *)((char *)Buffer + 8) = *a2;
    inserted = RtlInsertElementGenericTable(&WinHvpStatsTable, Buffer, 0x30u, NewElement);
    *(_QWORD *)Pool = inserted;
    if ( !inserted )
    {
      v11 = -1073741670;
LABEL_16:
      WinHvpFreePoolWithTag(Pool, 1333151831);
      if ( v4 )
        RtlDeleteElementGenericTable(&WinHvpStatsTable, Buffer);
      goto LABEL_18;
    }
    v4 = 1;
    ++inserted[8];
    if ( !NewElement[0] )
    {
      v11 = 0;
      v14 = *(_QWORD *)(*(_QWORD *)Pool + 40LL);
LABEL_9:
      *a3 = v14;
      *a4 = Pool;
LABEL_18:
      ExReleaseFastMutex(&WinHvpStatsTableLock);
      return (unsigned int)v11;
    }
    v11 = WinHvpIssueMapStatsPageHypercall(v13, a1, a2, &v18);
    if ( v11 >= 0 )
    {
      v15 = v18 << 12;
      v16 = MmMapIoSpaceEx(v18 << 12, 4096, 4);
      v14 = v16;
      if ( v16 )
      {
        *(_QWORD *)(*(_QWORD *)Pool + 40LL) = v16;
        *(_QWORD *)(*(_QWORD *)Pool + 24LL) = v15 >> 12;
        goto LABEL_9;
      }
      v11 = -1073741670;
    }
    if ( v18 != -1 && (unsigned __int8)WinHvIsOverlayMapLocationRequired() )
      WinHvpFreeOverlayPhysicalPage(v18);
    goto LABEL_16;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x140023350  push    rbp
0x140023352  push    rbx
0x140023353  push    rsi
0x140023354  push    rdi
0x140023355  push    r12
0x140023357  push    r13
0x140023359  push    r14
0x14002335b  mov     rbp, rsp
0x14002335e  sub     rsp, 70h
0x140023362  mov     rax, cs:__security_cookie
0x140023369  xor     rax, rsp
0x14002336c  mov     [rbp+var_10], rax
0x140023370  xor     r14d, r14d
0x140023373  mov     [rbp+var_48], 0FFFFFFFFFFFFFFFFh
0x14002337b  xorps   xmm0, xmm0
0x14002337e  mov     [r8], r14
0x140023381  xor     eax, eax
0x140023383  mov     [r9], r14
0x140023386  cmp     cs:WinHvpConnected, r14b
0x14002338d  mov     r13, r9
0x140023390  movups  [rbp+var_30], xmm0
0x140023394  mov     r12, r8
0x140023397  mov     rdi, rdx
0x14002339a  movups  [rbp+var_30+0Ch], xmm0
0x14002339e  mov     ebx, ecx
0x1400233a0  mov     [rbp+NewElement], r14b
0x1400233a4  movups  [rbp+Buffer], xmm0
0x1400233a8  jnz     short loc_1400233B4
0x1400233aa  mov     eax, 0C0350002h
0x1400233af  jmp     loc_1400234FF
0x1400233b4  mov     edx, 8
0x1400233b9  mov     ecx, 102h
0x1400233be  mov     r8d, 4F764857h
0x1400233c4  call    WinHvpAllocatePool
0x1400233c9  mov     rsi, rax
0x1400233cc  test    rax, rax
0x1400233cf  jnz     short loc_1400233DB
0x1400233d1  mov     edi, 0C000009Ah
0x1400233d6  jmp     loc_1400234FD
0x1400233db  lea     rcx, WinHvpStatsTableLock; FastMutex
0x1400233e2  call    cs:__imp_ExAcquireFastMutex
0x1400233e9  nop     dword ptr [rax+rax+00h]
0x1400233ee  xorps   xmm0, xmm0
0x1400233f1  lea     r9, [rbp+NewElement]; NewElement
0x1400233f5  movups  [rbp+Buffer], xmm0
0x1400233f9  mov     r8d, 30h ; '0'; BufferSize
0x1400233ff  lea     rdx, [rbp+Buffer]; Buffer
0x140023403  movups  [rbp+var_30], xmm0
0x140023407  lea     rcx, WinHvpStatsTable; Table
0x14002340e  mov     dword ptr [rbp+Buffer], ebx
0x140023411  movups  [rbp+var_20], xmm0
0x140023415  mov     dword ptr [rbp+var_20], r14d
0x140023419  movups  xmm0, xmmword ptr [rdi]
0x14002341c  movdqu  [rbp+Buffer+8], xmm0
0x140023421  call    cs:__imp_RtlInsertElementGenericTable
0x140023428  nop     dword ptr [rax+rax+00h]
0x14002342d  mov     [rsi], rax
0x140023430  test    rax, rax
0x140023433  jnz     short loc_14002343F
0x140023435  mov     edi, 0C000009Ah
0x14002343a  jmp     loc_1400234C1
0x14002343f  mov     r14d, 1
0x140023445  add     [rax+20h], r14d
0x140023449  cmp     [rbp+NewElement], 0
0x14002344d  jnz     short loc_140023465
0x14002344f  mov     rax, [rsi]
0x140023452  xor     edi, edi
0x140023454  mov     rcx, [rax+28h]
0x140023458  mov     [r12], rcx
0x14002345c  mov     [r13+0], rsi
0x140023460  jmp     loc_1400234EA
0x140023465  lea     r9, [rbp+var_48]
0x140023469  mov     r8, rdi
0x14002346c  mov     edx, ebx
0x14002346e  call    WinHvpIssueMapStatsPageHypercall
0x140023473  mov     edi, eax
0x140023475  test    eax, eax
0x140023477  js      short loc_1400234A8
0x140023479  mov     rbx, [rbp+var_48]
0x14002347d  mov     edx, 1000h
0x140023482  shl     rbx, 0Ch
0x140023486  mov     r8d, 4
0x14002348c  mov     rcx, rbx
0x14002348f  call    cs:__imp_MmMapIoSpaceEx
0x140023496  nop     dword ptr [rax+rax+00h]
0x14002349b  mov     rcx, rax
0x14002349e  test    rax, rax
0x1400234a1  jnz     short loc_14002351B
0x1400234a3  mov     edi, 0C000009Ah
0x1400234a8  cmp     [rbp+var_48], 0FFFFFFFFFFFFFFFFh
0x1400234ad  jz      short loc_1400234C1
0x1400234af  call    WinHvIsOverlayMapLocationRequired
0x1400234b4  test    al, al
0x1400234b6  jz      short loc_1400234C1
0x1400234b8  mov     rcx, [rbp+var_48]
0x1400234bc  call    WinHvpFreeOverlayPhysicalPage
0x1400234c1  mov     edx, 4F764857h
0x1400234c6  mov     rcx, rsi
0x1400234c9  call    WinHvpFreePoolWithTag
0x1400234ce  test    r14b, r14b
0x1400234d1  jz      short loc_1400234EA
0x1400234d3  lea     rdx, [rbp+Buffer]; Buffer
0x1400234d7  lea     rcx, WinHvpStatsTable; Table
0x1400234de  call    cs:__imp_RtlDeleteElementGenericTable
0x1400234e5  nop     dword ptr [rax+rax+00h]
0x1400234ea  lea     rcx, WinHvpStatsTableLock; FastMutex
0x1400234f1  call    cs:__imp_ExReleaseFastMutex
0x1400234f8  nop     dword ptr [rax+rax+00h]
0x1400234fd  mov     eax, edi
0x1400234ff  mov     rcx, [rbp+var_10]
0x140023503  xor     rcx, rsp; StackCookie
0x140023506  call    __security_check_cookie
0x14002350b  add     rsp, 70h
0x14002350f  pop     r14
0x140023511  pop     r13
0x140023513  pop     r12
0x140023515  pop     rdi
0x140023516  pop     rsi
0x140023517  pop     rbx
0x140023518  pop     rbp
0x140023519  retn
0x14002351b  mov     rax, [rsi]
0x14002351e  sar     rbx, 0Ch
0x140023522  mov     [rax+28h], rcx
0x140023526  mov     rax, [rsi]
0x140023529  mov     [rax+18h], rbx
0x14002352d  jmp     loc_140023458
```
