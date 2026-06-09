# ClientHandshakeProcessor::SaveExtensionValue(char const *,ulong,void *)

- ea: `0x18000aaf0`
- end: `0x18000ab44`
- name: `?SaveExtensionValue@ClientHandshakeProcessor@@CAJPEBDKPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(const char *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b394`
- `0x18000b438`

## pseudocode

```c
__int64 __fastcall ClientHandshakeProcessor::SaveExtensionValue(const char *a1, int a2, unsigned int *a3)
{
  const char *v7; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+28h] [rbp-20h]
  __int64 v9; // [rsp+2Ch] [rbp-1Ch]
  int v10; // [rsp+34h] [rbp-14h]

  Sqm::OnExtensionRequested(a1, a2);
  v9 = 0;
  v10 = 0;
  v7 = a1;
  v8 = a2;
  return List<ListVerifier::Element>::AddElement(a3 + 14, (__int64)&v7);
}

```

## disassembly

```asm
0x18000aaf0  mov     [rsp+arg_0], rbx
0x18000aaf5  mov     [rsp+arg_8], rsi
0x18000aafa  push    rdi
0x18000aafb  sub     rsp, 40h
0x18000aaff  mov     rsi, r8
0x18000ab02  mov     edi, edx
0x18000ab04  mov     rbx, rcx
0x18000ab07  call    ?OnExtensionRequested@Sqm@@SAXPEBDK@Z; Sqm::OnExtensionRequested(char const *,ulong)
0x18000ab0c  lea     rcx, [rsi+38h]
0x18000ab10  mov     [rsp+48h+var_1C], 0
0x18000ab19  lea     rdx, [rsp+48h+var_28]
0x18000ab1e  mov     [rsp+48h+var_14], 0
0x18000ab26  mov     [rsp+48h+var_28], rbx
0x18000ab2b  mov     [rsp+48h+var_20], edi
0x18000ab2f  call    ?AddElement@?$List@UElement@ListVerifier@@@@QEAAJPEAUElement@ListVerifier@@@Z; List<ListVerifier::Element>::AddElement(ListVerifier::Element *)
0x18000ab34  mov     rbx, [rsp+48h+arg_0]
0x18000ab39  mov     rsi, [rsp+48h+arg_8]
0x18000ab3e  add     rsp, 40h
0x18000ab42  pop     rdi
0x18000ab43  retn
```
