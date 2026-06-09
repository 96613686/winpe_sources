# KiServiceInternal

- ea: `0x1400f8940`
- end: `0x1400f8994`
- name: `KiServiceInternal`
- size: `84`
- prototype: ``
- caller_count: `78`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400ef540`
- `0x1400ef560`
- `0x1400ef580`
- `0x1400ef5a0`
- `0x1400ef5c0`
- `0x1400ef5e0`
- `0x1400ef600`
- `0x1400ef620`
- `0x1400ef640`
- `0x1400ef660`
- `0x1400ef680`
- `0x1400ef6a0`
- `0x1400ef6c0`
- `0x1400ef6e0`
- `0x1400ef700`
- `0x1400ef720`
- `0x1400ef740`
- `0x1400ef760`
- `0x1400ef780`
- `0x1400ef7a0`
- `0x1400ef7c0`
- `0x1400ef7e0`
- `0x1400ef800`
- `0x1400ef820`
- `0x1400ef840`
- `0x1400ef860`
- `0x1400ef880`
- `0x1400ef8a0`
- `0x1400ef8c0`
- `0x1400ef8e0`
- `0x1400ef900`
- `0x1400ef920`
- `0x1400ef940`
- `0x1400ef960`
- `0x1400ef980`
- `0x1400ef9a0`
- `0x1400ef9c0`
- `0x1400ef9e0`
- `0x1400efa00`
- `0x1400efa20`
- `0x1400efa40`
- `0x1400efa60`
- `0x1400efa80`
- `0x1400efaa0`
- `0x1400efac0`
- `0x1400efae0`
- `0x1400efb00`
- `0x1400efb20`
- `0x1400efb40`
- `0x1400efb60`

## callees

- `0x1400f89c0`

## pseudocode

```c
void KiServiceInternal()
{
  char *StackBase; // rbx

  _enable();
  StackBase = (char *)KeGetPcr()->NtTib.StackBase;
  _m_prefetchw(StackBase + 88);
  StackBase[96] = 0;
  JUMPOUT(0x1400F8C0ELL);
}

```

## disassembly

```asm
0x1400f8940  sub     rsp, 8
0x1400f8944  push    rbp
0x1400f8945  sub     rsp, 158h
0x1400f894c  lea     rbp, [rsp+80h]
0x1400f8954  mov     [rbp+0E8h+var_28], rbx
0x1400f895b  mov     [rbp+0E8h+var_20], rdi
0x1400f8962  mov     [rbp+0E8h+var_18], rsi
0x1400f8969  sti
0x1400f896a  mov     rbx, gs:8
0x1400f8973  prefetchw byte ptr [rbx+58h]
0x1400f8977  movzx   edi, byte ptr [rbx+60h]
0x1400f897b  mov     [rbp+0E8h+var_140], dil
0x1400f897f  mov     byte ptr [rbx+60h], 0
0x1400f8983  mov     r10, [rbx+58h]
0x1400f8987  mov     [rbp+0E8h+var_30], r10
0x1400f898e  jmp     KiSystemServiceStart
0x1400f8993  retn
```
