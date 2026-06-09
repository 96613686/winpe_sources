# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180010824`
- end: `0x18001086e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000cf28`
- `0x18000f4e8`
- `0x180010110`

## callees

- `0x18000aaf4`
- `0x180010824`

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
0x180010824  sub     rsp, 28h
0x180010828  lea     r8, [rcx+4]; Source
0x18001082c  cmp     [r8], edx
0x18001082f  jz      short loc_180010868
0x180010831  mov     al, [rcx+2]
0x180010834  mov     [r8], edx
0x180010837  cmp     al, 1
0x180010839  jnz     short loc_180010853
0x18001083b  mov     r9d, 2
0x180010841  mov     [rsp+28h+arg_8], dx
0x180010846  movzx   eax, dx
0x180010849  lea     r8, [rsp+28h+arg_8]
0x18001084e  mov     edx, r9d
0x180010851  jmp     short loc_18001085F
0x180010853  cmp     al, 2
0x180010855  jnz     short loc_180010868
0x180010857  mov     edx, 4; DestinationSize
0x18001085c  mov     r9d, edx; SourceSize
0x18001085f  mov     rcx, [rcx+10h]; Destination
0x180010863  call    memcpy_s
0x180010868  add     rsp, 28h
0x18001086c  retn
```
