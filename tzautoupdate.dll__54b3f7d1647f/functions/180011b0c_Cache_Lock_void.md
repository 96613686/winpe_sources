# Cache::Lock(void)

- ea: `0x180011b0c`
- end: `0x180011b29`
- name: `?Lock@Cache@@QEAA?AVProxy@1@XZ`
- size: `29`
- prototype: `Cache::Proxy *__fastcall(struct Cache *, Cache::Proxy *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180010784`
- `0x180010afc`
- `0x18001126c`
- `0x180011ff0`
- `0x180012178`
- `0x1800123b8`
- `0x180012628`
- `0x180012d38`
- `0x180012e80`
- `0x18001307c`
- `0x1800131dc`
- `0x180015750`

## callees

- `0x1800109a8`

## pseudocode

```c
Cache::Proxy *__fastcall Cache::Lock(struct Cache *a1, Cache::Proxy *a2)
{
  Cache::Proxy::Proxy(a2, a1);
  return a2;
}

```

## disassembly

```asm
0x180011b0c  push    rbx
0x180011b0e  sub     rsp, 20h
0x180011b12  mov     rbx, rdx
0x180011b15  mov     rdx, rcx; struct Cache *
0x180011b18  mov     rcx, rbx; this
0x180011b1b  call    ??0Proxy@Cache@@AEAA@PEAV1@@Z; Cache::Proxy::Proxy(Cache *)
0x180011b20  mov     rax, rbx
0x180011b23  add     rsp, 20h
0x180011b27  pop     rbx
0x180011b28  retn
```
