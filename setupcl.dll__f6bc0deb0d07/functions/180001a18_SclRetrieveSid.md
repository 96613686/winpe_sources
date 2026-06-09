# SclRetrieveSid

- ea: `0x180001a18`
- end: `0x180001b92`
- name: `SclRetrieveSid`
- size: `378`
- prototype: `__int64 __fastcall(HANDLE, const WCHAR *, const WCHAR *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800073c4`

## callees

- `0x1800014e8`
- `0x180001a18`
- `0x180009668`
- `0x18000a524`
- `0x1800179ad`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001af1`
- `ntdll!RtlAllocateHeap` at `0x180001af1`
- `ntdll!NtClose` at `0x180001b51`
- `ntdll!NtClose` at `0x180001b51`
- `ntdll!RtlFreeHeap` at `0x180001b6e`
- `ntdll!RtlFreeHeap` at `0x180001b6e`

## string_xrefs

- `0x180001a91`: `(%lx): Failed to open key [%ws]!`
- `0x180001aa5`: `SclRetrieveSid`
- `0x180001b18`: `SclRetrieveSid`

## pseudocode

```c
__int64 __fastcall SclRetrieveSid(HANDLE a1, const WCHAR *a2, const WCHAR *a3, _QWORD *a4)
{
  unsigned int *v7; // rbx
  int Key; // eax
  unsigned int v9; // edi
  int Value; // eax
  PVOID Heap; // rax
  ULONG v13; // [rsp+20h] [rbp-48h]
  HANDLE Handle[2]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int *v15; // [rsp+70h] [rbp+8h] BYREF

  if ( !a1 && !a2 || !a3 || !a4 )
    return 3221225485LL;
  v7 = 0;
  Handle[0] = 0;
  v15 = 0;
  if ( !a2 )
    goto LABEL_9;
  Key = SclCreateKey((__int64)a1, a2, 0xF003Fu, (__int64)Handle);
  v9 = Key;
  if ( Key >= 0 )
  {
    a1 = Handle[0];
LABEL_9:
    Value = SclRegGetValue(a1, a3, 16, &v15, v13);
    v7 = v15;
    v9 = Value;
    if ( Value >= 0 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15[2]);
      *a4 = Heap;
      if ( Heap )
      {
        memcpy_0(Heap, v7 + 3, v7[2]);
      }
      else
      {
        v9 = -1073741801;
        SclLogGenericMessage(
          0,
          3,
          (int)SclEvent_Generic_Error,
          258,
          (__int64)"SclRetrieveSid",
          "Call to SclAlloc failed!");
      }
    }
    goto LABEL_13;
  }
  SclLogGenericMessage(
    0,
    3,
    (int)SclEvent_Generic_Error,
    237,
    (__int64)"SclRetrieveSid",
    "(%lx): Failed to open key [%ws]!",
    Key,
    a2);
LABEL_13:
  if ( Handle[0] )
    NtClose(Handle[0]);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return v9;
}

```

## disassembly

```asm
0x180001a18  mov     [rsp+arg_8], rbx
0x180001a1d  mov     [rsp+arg_10], rbp
0x180001a22  push    rsi
0x180001a23  push    rdi
0x180001a24  push    r14
0x180001a26  sub     rsp, 50h
0x180001a2a  mov     r14, r9
0x180001a2d  mov     rbp, r8
0x180001a30  mov     rsi, rdx
0x180001a33  test    rcx, rcx
0x180001a36  jnz     short loc_180001A41
0x180001a38  test    rdx, rdx
0x180001a3b  jz      loc_180001B78
0x180001a41  test    rbp, rbp
0x180001a44  jz      loc_180001B78
0x180001a4a  test    r14, r14
0x180001a4d  jz      loc_180001B78
0x180001a53  xor     ebx, ebx
0x180001a55  mov     [rsp+68h+Handle], 0
0x180001a5e  mov     [rsp+68h+arg_0], rbx
0x180001a63  test    rsi, rsi
0x180001a66  jz      short loc_180001AC0
0x180001a68  lea     r9, [rsp+68h+Handle]
0x180001a6d  mov     r8d, 0F003Fh
0x180001a73  call    SclCreateKey
0x180001a78  mov     edi, eax
0x180001a7a  test    eax, eax
0x180001a7c  jns     short loc_180001ABB
0x180001a7e  mov     [rsp+68h+var_30], rsi
0x180001a83  lea     r8, SclEvent_Generic_Error
0x180001a8a  mov     [rsp+68h+var_38], eax
0x180001a8e  lea     edx, [rbx+3]
0x180001a91  lea     rax, aLxFailedToOpen_1; "(%lx): Failed to open key [%ws]!"
0x180001a98  mov     r9d, 0EDh
0x180001a9e  mov     [rsp+68h+var_40], rax
0x180001aa3  xor     ecx, ecx
0x180001aa5  lea     rax, aSclretrievesid; "SclRetrieveSid"
0x180001aac  mov     [rsp+68h+var_48], rax
0x180001ab1  call    SclLogGenericMessage
0x180001ab6  jmp     loc_180001B47
0x180001abb  mov     rcx, [rsp+68h+Handle]; KeyHandle
0x180001ac0  lea     r9, [rsp+68h+arg_0]
0x180001ac5  mov     r8d, 10h
0x180001acb  mov     rdx, rbp
0x180001ace  call    SclRegGetValue
0x180001ad3  mov     rbx, [rsp+68h+arg_0]
0x180001ad8  mov     edi, eax
0x180001ada  test    eax, eax
0x180001adc  js      short loc_180001B47
0x180001ade  mov     rcx, gs:60h
0x180001ae7  xor     edx, edx; Flags
0x180001ae9  mov     r8d, [rbx+8]; Size
0x180001aed  mov     rcx, [rcx+30h]; HeapHandle
0x180001af1  call    cs:__imp_RtlAllocateHeap
0x180001af7  mov     [r14], rax
0x180001afa  test    rax, rax
0x180001afd  jnz     short loc_180001B37
0x180001aff  lea     rax, aCallToSclalloc; "Call to SclAlloc failed!"
0x180001b06  mov     r9d, 102h
0x180001b0c  mov     [rsp+68h+var_40], rax
0x180001b11  lea     r8, SclEvent_Generic_Error
0x180001b18  lea     rax, aSclretrievesid; "SclRetrieveSid"
0x180001b1f  mov     edx, 3
0x180001b24  xor     ecx, ecx
0x180001b26  mov     [rsp+68h+var_48], rax
0x180001b2b  mov     edi, 0C0000017h
0x180001b30  call    SclLogGenericMessage
0x180001b35  jmp     short loc_180001B47
0x180001b37  mov     r8d, [rbx+8]; Size
0x180001b3b  lea     rdx, [rbx+0Ch]; Src
0x180001b3f  mov     rcx, rax; void *
0x180001b42  call    memcpy_0
0x180001b47  mov     rcx, [rsp+68h+Handle]; Handle
0x180001b4c  test    rcx, rcx
0x180001b4f  jz      short loc_180001B57
0x180001b51  call    cs:__imp_NtClose
0x180001b57  test    rbx, rbx
0x180001b5a  jz      short loc_180001B74
0x180001b5c  mov     rcx, gs:60h
0x180001b65  mov     r8, rbx; P
0x180001b68  xor     edx, edx; Flags
0x180001b6a  mov     rcx, [rcx+30h]; HeapHandle
0x180001b6e  call    cs:__imp_RtlFreeHeap
0x180001b74  mov     eax, edi
0x180001b76  jmp     short loc_180001B7D
0x180001b78  mov     eax, 0C000000Dh
0x180001b7d  lea     r11, [rsp+68h+var_18]
0x180001b82  mov     rbx, [r11+28h]
0x180001b86  mov     rbp, [r11+30h]
0x180001b8a  mov     rsp, r11
0x180001b8d  pop     r14
0x180001b8f  pop     rdi
0x180001b90  pop     rsi
0x180001b91  retn
```
