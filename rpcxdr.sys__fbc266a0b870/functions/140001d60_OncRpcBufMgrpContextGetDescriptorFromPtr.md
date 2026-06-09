# OncRpcBufMgrpContextGetDescriptorFromPtr

- ea: `0x140001d60`
- end: `0x140001ddd`
- name: `OncRpcBufMgrpContextGetDescriptorFromPtr`
- size: `125`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64, char)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140001458`
- `0x140001bf0`
- `0x140001cac`
- `0x140001de4`
- `0x140001e90`
- `0x140001ef0`
- `0x14000aac4`

## callees

- `0x140001d60`

## pseudocode

```c
__int64 *__fastcall OncRpcBufMgrpContextGetDescriptorFromPtr(__int64 a1, unsigned __int64 a2, char a3)
{
  __int64 v3; // r9
  unsigned __int64 v5; // r10
  __int64 *i; // r8
  unsigned __int64 v7; // r9
  bool v8; // cf

  v3 = *(_QWORD *)(a1 + 40);
  v5 = *(_QWORD *)(v3 + 56);
  if ( v5 > a2 )
    goto LABEL_4;
  if ( !a3 )
  {
    if ( a2 >= v5 + *(unsigned int *)(v3 + 72) )
      goto LABEL_4;
    return *(__int64 **)(a1 + 40);
  }
  if ( a2 < v5 + *(unsigned int *)(v3 + 76) )
    return *(__int64 **)(a1 + 40);
LABEL_4:
  for ( i = *(__int64 **)(a1 + 24); i != (__int64 *)(a1 + 24); i = (__int64 *)*i )
  {
    v7 = i[4];
    if ( a3 )
    {
      if ( v7 > a2 )
        continue;
      v8 = a2 < v7 + *((unsigned int *)i + 13);
    }
    else
    {
      if ( v7 > a2 )
        continue;
      v8 = a2 < i[5];
    }
    if ( v8 )
      return i - 3;
  }
  return 0;
}

```

## disassembly

```asm
0x140001d60  mov     [rsp+arg_0], rbx
0x140001d65  mov     r9, [rcx+28h]
0x140001d69  mov     bl, r8b
0x140001d6c  mov     r11, rcx
0x140001d6f  mov     r10, [r9+38h]
0x140001d73  cmp     r10, rdx
0x140001d76  ja      short loc_140001D88
0x140001d78  test    bl, bl
0x140001d7a  jz      short loc_140001DAD
0x140001d7c  mov     eax, [r9+4Ch]
0x140001d80  add     rax, r10
0x140001d83  cmp     rdx, rax
0x140001d86  jb      short loc_140001DB9
0x140001d88  lea     r10, [r11+18h]
0x140001d8c  mov     r8, [r10]
0x140001d8f  cmp     r8, r10
0x140001d92  jz      short loc_140001DD4
0x140001d94  mov     r9, [r8+20h]
0x140001d98  test    bl, bl
0x140001d9a  jz      short loc_140001DBE
0x140001d9c  cmp     r9, rdx
0x140001d9f  ja      short loc_140001DC9
0x140001da1  mov     eax, [r8+34h]
0x140001da5  add     rax, r9
0x140001da8  cmp     rdx, rax
0x140001dab  jmp     short loc_140001DC7
0x140001dad  mov     ecx, [r9+48h]
0x140001db1  add     rcx, r10
0x140001db4  cmp     rdx, rcx
0x140001db7  jnb     short loc_140001D88
0x140001db9  mov     rax, r9
0x140001dbc  jmp     short loc_140001DD6
0x140001dbe  cmp     r9, rdx
0x140001dc1  ja      short loc_140001DC9
0x140001dc3  cmp     rdx, [r8+28h]
0x140001dc7  jb      short loc_140001DCE
0x140001dc9  mov     r8, [r8]
0x140001dcc  jmp     short loc_140001D8F
0x140001dce  lea     rax, [r8-18h]
0x140001dd2  jmp     short loc_140001DD6
0x140001dd4  xor     eax, eax
0x140001dd6  mov     rbx, [rsp+arg_0]
0x140001ddb  retn
```
