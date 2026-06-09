# TSFreeString(_UNICODE_STRING *)

- ea: `0x180008810`
- end: `0x180008839`
- name: `?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z`
- size: `41`
- prototype: `void __fastcall(struct _UNICODE_STRING *)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180008840`
- `0x180009c6c`
- `0x180009cac`
- `0x180013468`
- `0x18001449c`
- `0x180015304`
- `0x1800161a0`
- `0x180016b38`
- `0x180017314`
- `0x1800182f0`
- `0x180018cf8`
- `0x1800190bc`
- `0x18001a12c`
- `0x18001a3e0`
- `0x18001a820`
- `0x18001a914`
- `0x18001b810`

## callees

- `0x180005ed0`
- `0x180008810`

## pseudocode

```c
void __fastcall TSFreeString(struct _UNICODE_STRING *a1)
{
  PWSTR Buffer; // rcx

  if ( a1 )
  {
    Buffer = a1->Buffer;
    if ( Buffer )
    {
      TSFree(Buffer);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x180008810  test    rcx, rcx
0x180008813  jz      short locret_18000882B
0x180008815  push    rbx
0x180008816  sub     rsp, 20h
0x18000881a  mov     rbx, rcx
0x18000881d  mov     rcx, [rcx+8]; void *
0x180008821  test    rcx, rcx
0x180008824  jnz     short loc_18000882C
0x180008826  add     rsp, 20h
0x18000882a  pop     rbx
0x18000882b  retn
0x18000882c  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180008831  xorps   xmm0, xmm0
0x180008834  movups  xmmword ptr [rbx], xmm0
0x180008837  jmp     short loc_180008826
```
