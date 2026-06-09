# WinNatDeleteBindingsForAddress

- ea: `0x14000a7dc`
- end: `0x14000a95d`
- name: `WinNatDeleteBindingsForAddress`
- size: `385`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001915c`
- `0x140019320`
- `0x140019428`
- `0x140019adc`

## callees

- `0x14000a7dc`
- `0x14000caa0`
- `0x140019edc`
- `0x14001a23c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a8fb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a8fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a82b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a82b`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14000a862`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14000a862`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14000a8cf`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14000a8cf`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14000a8eb`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14000a8eb`

## pseudocode

```c
__int64 **__fastcall WinNatDeleteBindingsForAddress(__int64 a1, _DWORD *a2, unsigned __int16 a3, unsigned __int16 a4)
{
  int i; // edx
  __int64 p_Blink; // rbx
  __int64 Signature; // rdx
  unsigned __int16 v11; // ax
  __int64 *v12; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rbx
  __int64 **result; // rax
  __int64 *v19; // rax
  __int64 *v20; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v21; // [rsp+28h] [rbp-50h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+48h] [rbp-30h] BYREF

  v21 = (__int64 *)&v20;
  v20 = (__int64 *)&v20;
  memset(&Enumerator, 0, sizeof(Enumerator));
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 64), &LockHandle);
  for ( i = 0; i <= *(_DWORD *)(a1 + 72); ++i )
  {
    while ( *(_DWORD *)(((__int64)i << 6) + a1 + 128) )
      ;
  }
  RtlInitWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
  while ( 1 )
  {
    v13 = RtlWeaklyEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
    if ( !v13 )
      break;
    p_Blink = (__int64)&v13[-1].Linkage.Blink;
    Signature = v13[3].Signature;
    if ( *(_DWORD *)(Signature + 4) == *a2 )
    {
      v11 = __ROR2__(*(_WORD *)(Signature + 2), 8);
      if ( a3 <= v11 && v11 <= a4 && !*(_DWORD *)(p_Blink + 64) )
      {
        WinNatFreeBindingUnderLock(p_Blink, Signature, v14);
        v12 = v21;
        if ( (__int64 **)*v21 != &v20 )
LABEL_19:
          __fastfail(3u);
        *(_QWORD *)(p_Blink + 8) = v21;
        *(_QWORD *)p_Blink = &v20;
        *v12 = p_Blink;
        v21 = (__int64 *)p_Blink;
      }
    }
  }
  RtlEndWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v17 = v20;
    result = &v20;
    if ( v20 == (__int64 *)&v20 )
      return result;
    if ( (__int64 **)v20[1] != &v20 )
      goto LABEL_19;
    v19 = (__int64 *)*v20;
    if ( *(__int64 **)(*v20 + 8) != v20 )
      goto LABEL_19;
    v20 = (__int64 *)*v20;
    v19[1] = (__int64)&v20;
    if ( *((_DWORD *)v17 + 16) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(&v20, v15, v16);
    WinNatCleanupBinding(v17);
  }
}

```

## disassembly

```asm
0x14000a7dc  push    rbp
0x14000a7de  push    rbx
0x14000a7df  push    rsi
0x14000a7e0  push    rdi
0x14000a7e1  push    r14
0x14000a7e3  push    r15
0x14000a7e5  mov     rbp, rsp
0x14000a7e8  sub     rsp, 78h
0x14000a7ec  xor     eax, eax
0x14000a7ee  xorps   xmm0, xmm0
0x14000a7f1  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x14000a7f5  mov     r15, rdx
0x14000a7f8  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000a7fc  lea     rdx, [rbp+LockHandle]; LockHandle
0x14000a800  lea     rax, [rbp+var_58]
0x14000a804  mov     rdi, rcx
0x14000a807  mov     [rbp+var_50], rax
0x14000a80b  add     rcx, 40h ; '@'; SpinLock
0x14000a80f  lea     rax, [rbp+var_58]
0x14000a813  movzx   esi, r9w
0x14000a817  mov     [rbp+var_58], rax
0x14000a81b  movzx   r14d, r8w
0x14000a81f  movups  xmmword ptr [rbp+Enumerator], xmm0
0x14000a823  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x14000a827  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000a82b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a832  nop     dword ptr [rax+rax+00h]
0x14000a837  xor     edx, edx
0x14000a839  cmp     [rdi+48h], edx
0x14000a83c  jl      short loc_14000A857
0x14000a83e  movsxd  rcx, edx
0x14000a841  shl     rcx, 6
0x14000a845  mov     eax, [rcx+rdi+80h]
0x14000a84c  test    eax, eax
0x14000a84e  jnz     short loc_14000A845
0x14000a850  inc     edx
0x14000a852  cmp     edx, [rdi+48h]
0x14000a855  jle     short loc_14000A83E
0x14000a857  mov     rcx, [rdi+180h]; HashTable
0x14000a85e  lea     rdx, [rbp+Enumerator]; Enumerator
0x14000a862  call    cs:__imp_RtlInitWeakEnumerationHashTable
0x14000a869  nop     dword ptr [rax+rax+00h]
0x14000a86e  jmp     short loc_14000A8C4
0x14000a870  lea     rbx, [rax-10h]
0x14000a874  mov     rdx, [rbx+68h]
0x14000a878  mov     ecx, [rdx+4]
0x14000a87b  cmp     ecx, [r15]
0x14000a87e  jnz     short loc_14000A8C4
0x14000a880  movzx   eax, word ptr [rdx+2]
0x14000a884  ror     ax, 8
0x14000a888  cmp     r14w, ax
0x14000a88c  ja      short loc_14000A8C4
0x14000a88e  cmp     ax, si
0x14000a891  ja      short loc_14000A8C4
0x14000a893  cmp     dword ptr [rbx+40h], 0
0x14000a897  jnz     short loc_14000A8C4
0x14000a899  mov     rcx, rbx
0x14000a89c  call    WinNatFreeBindingUnderLock
0x14000a8a1  mov     rax, [rbp+var_50]
0x14000a8a5  lea     rcx, [rbp+var_58]
0x14000a8a9  cmp     [rax], rcx
0x14000a8ac  jnz     loc_14000A948
0x14000a8b2  mov     [rbx+8], rax
0x14000a8b6  lea     rcx, [rbp+var_58]
0x14000a8ba  mov     [rbx], rcx
0x14000a8bd  mov     [rax], rbx
0x14000a8c0  mov     [rbp+var_50], rbx
0x14000a8c4  mov     rcx, [rdi+180h]; HashTable
0x14000a8cb  lea     rdx, [rbp+Enumerator]; Enumerator
0x14000a8cf  call    cs:__imp_RtlWeaklyEnumerateEntryHashTable
0x14000a8d6  nop     dword ptr [rax+rax+00h]
0x14000a8db  test    rax, rax
0x14000a8de  jnz     short loc_14000A870
0x14000a8e0  mov     rcx, [rdi+180h]; HashTable
0x14000a8e7  lea     rdx, [rbp+Enumerator]; Enumerator
0x14000a8eb  call    cs:__imp_RtlEndWeakEnumerationHashTable
0x14000a8f2  nop     dword ptr [rax+rax+00h]
0x14000a8f7  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000a8fb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000a902  nop     dword ptr [rax+rax+00h]
0x14000a907  mov     rbx, [rbp+var_58]
0x14000a90b  lea     rax, [rbp+var_58]
0x14000a90f  cmp     rbx, rax
0x14000a912  jz      short loc_14000A94F
0x14000a914  lea     rax, [rbp+var_58]
0x14000a918  cmp     [rbx+8], rax
0x14000a91c  jnz     short loc_14000A948
0x14000a91e  mov     rax, [rbx]
0x14000a921  cmp     [rax+8], rbx
0x14000a925  jnz     short loc_14000A948
0x14000a927  mov     [rbp+var_58], rax
0x14000a92b  lea     rcx, [rbp+var_58]
0x14000a92f  mov     [rax+8], rcx
0x14000a933  cmp     dword ptr [rbx+40h], 0
0x14000a937  jz      short loc_14000A93E
0x14000a939  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000a93e  mov     rcx, rbx
0x14000a941  call    WinNatCleanupBinding
0x14000a946  jmp     short loc_14000A907
0x14000a948  mov     ecx, 3
0x14000a94d  int     29h; Win8: RtlFailFast(ecx)
0x14000a94f  add     rsp, 78h
0x14000a953  pop     r15
0x14000a955  pop     r14
0x14000a957  pop     rdi
0x14000a958  pop     rsi
0x14000a959  pop     rbx
0x14000a95a  pop     rbp
0x14000a95b  retn
```
