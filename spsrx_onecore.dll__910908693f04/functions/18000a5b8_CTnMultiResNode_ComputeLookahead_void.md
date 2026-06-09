# CTnMultiResNode::ComputeLookahead(void)

- ea: `0x18000a5b8`
- end: `0x18000a60d`
- name: `?ComputeLookahead@CTnMultiResNode@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(CTnMultiResNode *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000de0c`

## callees

- `0x18000a5b8`

## pseudocode

```c
void __fastcall CTnMultiResNode::ComputeLookahead(CTnMultiResNode *this)
{
  bool v1; // cc
  int v2; // r11d
  _QWORD *v3; // r9
  int v4; // ebx
  int v5; // r8d
  __int64 v6; // rax

  v1 = *((_DWORD *)this + 22) <= 0;
  v2 = *((_DWORD *)this + 11);
  *((_DWORD *)this + 12) = v2;
  if ( !v1 )
  {
    v3 = (_QWORD *)*((_QWORD *)this + 9);
    if ( v3 )
    {
      v4 = 0;
      v5 = v2;
      do
      {
        v6 = v3[2];
        v3 = (_QWORD *)*v3;
        if ( !v4 || v2 + *(_DWORD *)(v6 + 48) < v5 )
        {
          v4 = 1;
          v5 = v2 + *(_DWORD *)(v6 + 48);
          *((_DWORD *)this + 12) = v5;
        }
      }
      while ( v3 );
    }
  }
}

```

## disassembly

```asm
0x18000a5b8  mov     [rsp+arg_0], rbx
0x18000a5bd  cmp     dword ptr [rcx+58h], 0
0x18000a5c1  mov     rdx, rcx
0x18000a5c4  mov     r11d, [rcx+2Ch]
0x18000a5c8  mov     [rcx+30h], r11d
0x18000a5cc  jle     short loc_18000A607
0x18000a5ce  mov     r9, [rcx+48h]
0x18000a5d2  test    r9, r9
0x18000a5d5  jz      short loc_18000A607
0x18000a5d7  xor     ebx, ebx
0x18000a5d9  mov     r8d, r11d
0x18000a5dc  mov     rax, [r9+10h]
0x18000a5e0  mov     r9, [r9]
0x18000a5e3  test    ebx, ebx
0x18000a5e5  jz      short loc_18000A5F2
0x18000a5e7  mov     ecx, [rax+30h]
0x18000a5ea  add     ecx, r11d
0x18000a5ed  cmp     ecx, r8d
0x18000a5f0  jge     short loc_18000A602
0x18000a5f2  mov     r8d, [rax+30h]
0x18000a5f6  mov     ebx, 1
0x18000a5fb  add     r8d, r11d
0x18000a5fe  mov     [rdx+30h], r8d
0x18000a602  test    r9, r9
0x18000a605  jnz     short loc_18000A5DC
0x18000a607  mov     rbx, [rsp+arg_0]
0x18000a60c  retn
```
