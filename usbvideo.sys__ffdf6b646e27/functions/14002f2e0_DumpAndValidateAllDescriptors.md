# DumpAndValidateAllDescriptors

- ea: `0x14002f2e0`
- end: `0x14002f3e2`
- name: `DumpAndValidateAllDescriptors`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140015e60`

## callees

- `0x14002f2e0`
- `0x14002f590`
- `0x14002fd58`
- `0x140030208`
- `0x1400304ac`
- `0x14003580c`
- `0x140037068`

## pseudocode

```c
__int64 __fastcall DumpAndValidateAllDescriptors(__int64 a1)
{
  unsigned __int8 *v1; // rbx
  bool v2; // zf
  __int64 v4; // rdi
  int v5; // esi
  unsigned int v6; // ecx
  unsigned __int64 v7; // rdi
  int v8; // eax
  unsigned __int16 v9; // [rsp+30h] [rbp+8h] BYREF

  v1 = (unsigned __int8 *)a1;
  v2 = *(_BYTE *)(a1 + 1) == 2;
  v9 = 0;
  if ( !v2 )
    return 3221225473LL;
  v4 = *(unsigned __int16 *)(a1 + 2);
  v5 = 0;
  v6 = 0;
  v7 = (unsigned __int64)&v1[v4];
  while ( (unsigned __int64)v1 < v7 )
  {
    if ( (unsigned __int64)(v1 + 2) > v7 || (unsigned __int64)&v1[*v1] > v7 )
      return (unsigned int)-1073741823;
    if ( v1[1] == 2 )
    {
      v8 = DumpAndValidateConfigDescriptor(v1, v7);
    }
    else
    {
      if ( v1[1] != 3 )
      {
        switch ( v1[1] )
        {
          case 4u:
            v6 = DumpAndValidateInterfaceDescriptor(v1, v7);
            if ( (v6 & 0x80000000) != 0 )
              return v6;
            v5 = v1[6];
            goto LABEL_21;
          case 5u:
            v8 = DumpAndValidateEndpointDescriptor(v1, v7);
            goto LABEL_20;
          case 0x24u:
            v8 = DumpAndValidateClassSpecInterfaceDescriptor(v1, v7, v5, &v9);
            goto LABEL_20;
          case 0x25u:
            v8 = DumpAndValidateClassSpecificEndpointDescriptor(v1, v7);
            goto LABEL_20;
        }
      }
      v8 = DumpAndValidateGenericDescriptor(v1, v7);
    }
LABEL_20:
    v6 = v8;
    if ( v8 < 0 )
      return v6;
LABEL_21:
    v1 += *v1;
  }
  return v6;
}

```

## disassembly

```asm
0x14002f2e0  mov     [rsp+arg_8], rbx
0x14002f2e5  mov     [rsp+arg_10], rsi
0x14002f2ea  push    rdi
0x14002f2eb  sub     rsp, 20h
0x14002f2ef  xor     eax, eax
0x14002f2f1  mov     rbx, rcx
0x14002f2f4  cmp     byte ptr [rcx+1], 2
0x14002f2f8  mov     [rsp+28h+arg_0], ax
0x14002f2fd  jz      short loc_14002F309
0x14002f2ff  mov     eax, 0C0000001h
0x14002f304  jmp     loc_14002F3D1
0x14002f309  movzx   edi, word ptr [rbx+2]
0x14002f30d  xor     esi, esi
0x14002f30f  xor     ecx, ecx
0x14002f311  add     rdi, rbx
0x14002f314  cmp     rbx, rdi
0x14002f317  jnb     loc_14002F3CF
0x14002f31d  lea     rax, [rbx+2]
0x14002f321  cmp     rax, rdi
0x14002f324  ja      loc_14002F3CA
0x14002f32a  movzx   eax, byte ptr [rbx]
0x14002f32d  add     rax, rbx
0x14002f330  cmp     rax, rdi
0x14002f333  ja      loc_14002F3CA
0x14002f339  movzx   ecx, byte ptr [rbx+1]
0x14002f33d  sub     ecx, 2
0x14002f340  jz      short loc_14002F3AE
0x14002f342  sub     ecx, 1
0x14002f345  jz      short loc_14002F3A1
0x14002f347  sub     ecx, 1
0x14002f34a  jz      short loc_14002F38A
0x14002f34c  sub     ecx, 1
0x14002f34f  jz      short loc_14002F37D
0x14002f351  sub     ecx, 1Fh
0x14002f354  jz      short loc_14002F368
0x14002f356  cmp     ecx, 1
0x14002f359  jnz     short loc_14002F3A1
0x14002f35b  mov     rdx, rdi
0x14002f35e  mov     rcx, rbx
0x14002f361  call    DumpAndValidateClassSpecificEndpointDescriptor
0x14002f366  jmp     short loc_14002F3B9
0x14002f368  lea     r9, [rsp+28h+arg_0]
0x14002f36d  mov     r8d, esi
0x14002f370  mov     rdx, rdi
0x14002f373  mov     rcx, rbx
0x14002f376  call    DumpAndValidateClassSpecInterfaceDescriptor
0x14002f37b  jmp     short loc_14002F3B9
0x14002f37d  mov     rdx, rdi
0x14002f380  mov     rcx, rbx
0x14002f383  call    DumpAndValidateEndpointDescriptor
0x14002f388  jmp     short loc_14002F3B9
0x14002f38a  mov     rdx, rdi
0x14002f38d  mov     rcx, rbx
0x14002f390  call    DumpAndValidateInterfaceDescriptor
0x14002f395  mov     ecx, eax
0x14002f397  test    eax, eax
0x14002f399  js      short loc_14002F3CF
0x14002f39b  movzx   esi, byte ptr [rbx+6]
0x14002f39f  jmp     short loc_14002F3BF
0x14002f3a1  mov     rdx, rdi
0x14002f3a4  mov     rcx, rbx
0x14002f3a7  call    DumpAndValidateGenericDescriptor
0x14002f3ac  jmp     short loc_14002F3B9
0x14002f3ae  mov     rdx, rdi
0x14002f3b1  mov     rcx, rbx
0x14002f3b4  call    DumpAndValidateConfigDescriptor
0x14002f3b9  mov     ecx, eax
0x14002f3bb  test    eax, eax
0x14002f3bd  js      short loc_14002F3CF
0x14002f3bf  movzx   eax, byte ptr [rbx]
0x14002f3c2  add     rbx, rax
0x14002f3c5  jmp     loc_14002F314
0x14002f3ca  mov     ecx, 0C0000001h
0x14002f3cf  mov     eax, ecx
0x14002f3d1  mov     rbx, [rsp+28h+arg_8]
0x14002f3d6  mov     rsi, [rsp+28h+arg_10]
0x14002f3db  add     rsp, 20h
0x14002f3df  pop     rdi
0x14002f3e0  retn
```
