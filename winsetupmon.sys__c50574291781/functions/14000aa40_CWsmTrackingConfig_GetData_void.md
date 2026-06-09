# CWsmTrackingConfig::GetData(void)

- ea: `0x14000aa40`
- end: `0x14000aa7f`
- name: `?GetData@CWsmTrackingConfig@@UEBAPEBEXZ`
- size: `63`
- prototype: `const unsigned __int8 *__fastcall(CWsmTrackingConfig *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000aa40`
- `0x14000f9e0`

## pseudocode

```c
__int64 (__fastcall **__fastcall CWsmTrackingConfig::GetData(__int64 (__fastcall ***this)(char *)))(char *)
{
  __int64 v2; // rax

  v2 = (**(this - 1))((char *)this - 8);
  if ( v2 && (*(_QWORD *)v2 || *(_QWORD *)(v2 + 8) || *(_DWORD *)(v2 + 16)) )
    return this[1];
  else
    return 0;
}

```

## disassembly

```asm
0x14000aa40  push    rbx
0x14000aa42  sub     rsp, 20h
0x14000aa46  mov     rbx, rcx
0x14000aa49  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000aa4d  mov     rax, [rcx]
0x14000aa50  mov     rax, [rax]
0x14000aa53  call    _guard_dispatch_icall
0x14000aa58  xor     ecx, ecx
0x14000aa5a  test    rax, rax
0x14000aa5d  jz      short loc_14000AA75
0x14000aa5f  cmp     [rax], rcx
0x14000aa62  jnz     short loc_14000AA6F
0x14000aa64  cmp     [rax+8], rcx
0x14000aa68  jnz     short loc_14000AA6F
0x14000aa6a  cmp     [rax+10h], ecx
0x14000aa6d  jz      short loc_14000AA75
0x14000aa6f  mov     rax, [rbx+8]
0x14000aa73  jmp     short loc_14000AA78
0x14000aa75  mov     rax, rcx
0x14000aa78  add     rsp, 20h
0x14000aa7c  pop     rbx
0x14000aa7d  retn
```
