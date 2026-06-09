# GetObjectAsyncThread(ushort *,long,IWbemObjectSink *,CImpDyn *,IWbemContext *)

- ea: `0x18000e060`
- end: `0x18000e0fd`
- name: `?GetObjectAsyncThread@@YAXPEAGJPEAUIWbemObjectSink@@PEAVCImpDyn@@PEAUIWbemContext@@@Z`
- size: `157`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, struct IWbemObjectSink *, struct CImpDyn *, struct IWbemContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dfd0`

## callees

- `0x18000e060`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetObjectAsyncThread(
        unsigned __int16 *a1,
        unsigned int a2,
        struct IWbemObjectSink *a3,
        struct CImpDyn *a4,
        struct IWbemContext *a5)
{
  __int64 (__fastcall *v6)(struct CImpDyn *, unsigned __int16 *, _QWORD, struct IWbemContext *, __int64 *, _QWORD); // rax
  unsigned int v7; // edi
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  v6 = *(__int64 (__fastcall **)(struct CImpDyn *, unsigned __int16 *, _QWORD, struct IWbemContext *, __int64 *, _QWORD))(*(_QWORD *)a4 + 48LL);
  v8 = 0;
  v7 = v6(a4, a1, a2, a5, &v8, 0);
  if ( !v7 )
  {
    ((void (__fastcall *)(struct IWbemObjectSink *, __int64, __int64 *))a3->lpVtbl->Indicate)(a3, 1, &v8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))a3->lpVtbl->SetStatus)(
    a3,
    0,
    v7,
    0,
    0);
}

```

## disassembly

```asm
0x18000e060  mov     r11, rsp
0x18000e063  mov     [r11+8], rbx
0x18000e067  push    rdi
0x18000e068  sub     rsp, 40h
0x18000e06c  mov     rax, [r9]
0x18000e06f  mov     rbx, r8
0x18000e072  lea     r8, [r11+18h]
0x18000e076  mov     qword ptr [r11-20h], 0
0x18000e07e  mov     r10, r9
0x18000e081  mov     [r11-28h], r8
0x18000e085  mov     r9, [rsp+48h+arg_20]
0x18000e08a  mov     r8d, edx
0x18000e08d  mov     rax, [rax+30h]
0x18000e091  mov     rdx, rcx
0x18000e094  mov     rcx, r10
0x18000e097  mov     qword ptr [r11+18h], 0
0x18000e09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0a4  mov     edi, eax
0x18000e0a6  test    eax, eax
0x18000e0a8  jnz     short loc_18000E0D2
0x18000e0aa  mov     rcx, [rbx]
0x18000e0ad  lea     r8, [rsp+48h+arg_10]
0x18000e0b2  lea     edx, [rdi+1]
0x18000e0b5  mov     rax, [rcx+18h]
0x18000e0b9  mov     rcx, rbx
0x18000e0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0c1  mov     rcx, [rsp+48h+arg_10]
0x18000e0c6  mov     rdx, [rcx]
0x18000e0c9  mov     rax, [rdx+10h]
0x18000e0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d2  mov     rax, [rbx]
0x18000e0d5  xor     r9d, r9d
0x18000e0d8  mov     r8d, edi
0x18000e0db  mov     [rsp+48h+var_28], 0
0x18000e0e4  xor     edx, edx
0x18000e0e6  mov     rcx, rbx
0x18000e0e9  mov     rax, [rax+20h]
0x18000e0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f2  mov     rbx, [rsp+48h+arg_0]
0x18000e0f7  add     rsp, 40h
0x18000e0fb  pop     rdi
0x18000e0fc  retn
```
