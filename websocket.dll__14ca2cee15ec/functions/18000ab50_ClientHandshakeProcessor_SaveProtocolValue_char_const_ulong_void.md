# ClientHandshakeProcessor::SaveProtocolValue(char const *,ulong,void *)

- ea: `0x18000ab50`
- end: `0x18000ab7f`
- name: `?SaveProtocolValue@ClientHandshakeProcessor@@CAJPEBDKPEAX@Z`
- size: `47`
- prototype: `__int64 __fastcall(const char *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b438`

## pseudocode

```c
__int64 __fastcall ClientHandshakeProcessor::SaveProtocolValue(const char *a1, int a2, unsigned int *a3)
{
  const char *v4; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+28h] [rbp-20h]
  __int64 v6; // [rsp+2Ch] [rbp-1Ch]
  int v7; // [rsp+34h] [rbp-14h]

  v4 = a1;
  v5 = a2;
  v6 = 0;
  v7 = 0;
  return List<ListVerifier::Element>::AddElement(a3 + 6, (__int64)&v4);
}

```

## disassembly

```asm
0x18000ab50  mov     rax, rsp
0x18000ab53  sub     rsp, 48h
0x18000ab57  mov     [rax-28h], rcx
0x18000ab5b  lea     rcx, [r8+18h]
0x18000ab5f  mov     [rax-20h], edx
0x18000ab62  lea     rdx, [rax-28h]
0x18000ab66  mov     qword ptr [rax-1Ch], 0
0x18000ab6e  mov     dword ptr [rax-14h], 0
0x18000ab75  call    ?AddElement@?$List@UElement@ListVerifier@@@@QEAAJPEAUElement@ListVerifier@@@Z; List<ListVerifier::Element>::AddElement(ListVerifier::Element *)
0x18000ab7a  add     rsp, 48h
0x18000ab7e  retn
```
