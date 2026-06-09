# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800099ac`
- end: `0x1800099f6`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000556c`
- `0x180007e38`
- `0x180008eb4`

## callees

- `0x1800099ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800099eb`
- `msvcrt!memcpy_s` at `0x1800099eb`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  __int16 *v2; // r8
  char v3; // al
  rsize_t v4; // r9
  rsize_t v5; // rdx
  __int16 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (__int16 *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) != a2 )
  {
    v3 = *((_BYTE *)this + 2);
    *(_DWORD *)v2 = a2;
    if ( v3 == 1 )
    {
      v4 = 2;
      v6 = a2;
      v2 = &v6;
      v5 = 2;
    }
    else
    {
      if ( v3 != 2 )
        return;
      v5 = 4;
      v4 = 4;
    }
    memcpy_s(*((void *const *)this + 2), v5, v2, v4);
  }
}

```

## disassembly

```asm
0x1800099ac  sub     rsp, 28h
0x1800099b0  lea     r8, [rcx+4]; Source
0x1800099b4  cmp     [r8], edx
0x1800099b7  jz      short loc_1800099F1
0x1800099b9  mov     al, [rcx+2]
0x1800099bc  mov     [r8], edx
0x1800099bf  cmp     al, 1
0x1800099c1  jnz     short loc_1800099DB
0x1800099c3  mov     r9d, 2
0x1800099c9  mov     [rsp+28h+arg_8], dx
0x1800099ce  movzx   eax, dx
0x1800099d1  lea     r8, [rsp+28h+arg_8]
0x1800099d6  mov     edx, r9d
0x1800099d9  jmp     short loc_1800099E7
0x1800099db  cmp     al, 2
0x1800099dd  jnz     short loc_1800099F1
0x1800099df  mov     edx, 4; DestinationSize
0x1800099e4  mov     r9d, edx; SourceSize
0x1800099e7  mov     rcx, [rcx+10h]; Destination
0x1800099eb  call    cs:__imp_memcpy_s
0x1800099f1  add     rsp, 28h
0x1800099f5  retn
```
