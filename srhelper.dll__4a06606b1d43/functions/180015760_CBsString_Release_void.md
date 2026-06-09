# CBsString::_Release(void)

- ea: `0x180015760`
- end: `0x180015798`
- name: `?_Release@CBsString@@AEAAXXZ`
- size: `56`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `29`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002054`
- `0x1800022e4`
- `0x180002658`
- `0x180002818`
- `0x1800029d8`
- `0x180002e9c`
- `0x180003360`
- `0x180003550`
- `0x180003968`
- `0x180003b24`
- `0x180004928`
- `0x180004e20`
- `0x1800050dc`
- `0x1800055a4`
- `0x18000572c`
- `0x18000a790`
- `0x18000ab80`
- `0x18000af70`
- `0x18000b3b0`
- `0x18000bbe0`
- `0x18000bdd0`
- `0x18000bf70`
- `0x18000c258`
- `0x18000c468`
- `0x18000c890`
- `0x18000ca98`
- `0x18000cc20`
- `0x18000e554`
- `0x18000e7ec`

## callees

- `0x180015760`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001577c`
- `ole32!CoTaskMemFree` at `0x18001577c`

## pseudocode

```c
void __fastcall CBsString::_Release(LPVOID *this)
{
  if ( *this != qword_18001A620 )
    CoTaskMemFree(*this);
  *this = qword_18001A620;
  this[1] = 0;
}

```

## disassembly

```asm
0x180015760  mov     [rsp+arg_0], rbx
0x180015765  push    rdi
0x180015766  sub     rsp, 20h
0x18001576a  lea     rdi, qword_18001A620
0x180015771  mov     rbx, rcx
0x180015774  cmp     [rcx], rdi
0x180015777  jz      short loc_180015782
0x180015779  mov     rcx, [rcx]; pv
0x18001577c  call    cs:__imp_CoTaskMemFree
0x180015782  mov     [rbx], rdi
0x180015785  mov     qword ptr [rbx+8], 0
0x18001578d  mov     rbx, [rsp+28h+arg_0]
0x180015792  add     rsp, 20h
0x180015796  pop     rdi
0x180015797  retn
```
