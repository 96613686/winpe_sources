# VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)

- ea: `0x14003acbc`
- end: `0x14003ace9`
- name: `?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z`
- size: `45`
- prototype: `int __fastcall(struct VMX_PACK *, struct VMX_PACK **)`
- caller_count: `23`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002b964`
- `0x14002eb3c`
- `0x14002f1e4`
- `0x1400302dc`
- `0x140030680`
- `0x140035180`
- `0x1400358f4`
- `0x140035e3c`
- `0x1400362a8`
- `0x14003695c`
- `0x140036bac`
- `0x140036e70`
- `0x140037fe4`
- `0x140039028`
- `0x140039d00`
- `0x140039f10`
- `0x14003b094`
- `0x14003b350`
- `0x14003b600`
- `0x14003bd90`
- `0x14003c660`
- `0x14003c870`
- `0x14003ccc0`

## callees

- `0x14003acbc`
- `0x14003acf0`
- `0x1400536d4`
- `0x140054b2c`

## pseudocode

```c
int __fastcall VmxpRecoverPackConfigOnline(struct VMX_PACK *a1, struct VMX_PACK **a2)
{
  struct VMX_PACK **v3; // rdx
  struct VMX_PACK *v4; // rcx
  int result; // eax

  *a2 = a1;
  if ( VMX_PACK::QuorumInSync(a1) )
    return VMX_PACK::OnlineConfig(*a2);
  result = VmxpRecoverPackQuorum(v4, v3);
  if ( result >= 0 )
    return VMX_PACK::OnlineConfig(*a2);
  return result;
}

```

## disassembly

```asm
0x14003acbc  push    rbx
0x14003acbe  sub     rsp, 20h
0x14003acc2  mov     rbx, rdx
0x14003acc5  mov     [rdx], rcx
0x14003acc8  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x14003accd  test    al, al
0x14003accf  jnz     short loc_14003ACDA
0x14003acd1  call    ?VmxpRecoverPackQuorum@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackQuorum(VMX_PACK *,VMX_PACK * *)
0x14003acd6  test    eax, eax
0x14003acd8  js      short loc_14003ACE2
0x14003acda  mov     rcx, [rbx]; this
0x14003acdd  call    ?OnlineConfig@VMX_PACK@@QEAAJXZ; VMX_PACK::OnlineConfig(void)
0x14003ace2  add     rsp, 20h
0x14003ace6  pop     rbx
0x14003ace7  retn
```
