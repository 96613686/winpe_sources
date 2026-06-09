# SIPolicyReleaseMutableState

- ea: `0x18001c9ac`
- end: `0x18001ca76`
- name: `SIPolicyReleaseMutableState`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180019cd0`
- `0x18001c148`
- `0x18001c6d4`
- `0x18001c76c`
- `0x18001ca7c`
- `0x1800492f8`

## callees

- `0x1800187d4`
- `0x18001c9ac`
- `0x18002019c`

## pseudocode

```c
void __fastcall SIPolicyReleaseMutableState(__int64 *a1)
{
  __int64 v1; // rbx
  _QWORD *v2; // rcx
  _QWORD *v3; // rdi
  _QWORD *v4; // rax
  _QWORD *v5; // rdx
  _QWORD *v6; // rcx
  _QWORD *v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rdx

  v1 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    v2 = *(_QWORD **)(v1 + 16);
    if ( v2 != (_QWORD *)(v1 + 16) )
    {
      v3 = (_QWORD *)*v2;
      v4 = (_QWORD *)*v2;
      while ( (_QWORD *)v4[1] == v2 )
      {
        v5 = (_QWORD *)v2[1];
        if ( (_QWORD *)*v5 != v2 )
          break;
        *v5 = v4;
        v4[1] = v5;
        SIPolicyUninitialize((__int64)(v2 - 104));
        if ( v3 == (_QWORD *)(v1 + 16) )
          goto LABEL_8;
        v4 = (_QWORD *)*v3;
        v2 = v3;
        v3 = (_QWORD *)*v3;
      }
LABEL_14:
      __fastfail(3u);
    }
LABEL_8:
    v6 = *(_QWORD **)(v1 + 32);
    if ( v6 != (_QWORD *)(v1 + 32) )
    {
      v7 = (_QWORD *)*v6;
      v8 = (_QWORD *)*v6;
      while ( (_QWORD *)v8[1] == v6 )
      {
        v9 = (_QWORD *)v6[1];
        if ( (_QWORD *)*v9 != v6 )
          break;
        *v9 = v8;
        v8[1] = v9;
        SIPolicyUninitialize((__int64)(v6 - 104));
        if ( v7 == (_QWORD *)(v1 + 32) )
          goto LABEL_15;
        v8 = (_QWORD *)*v7;
        v6 = v7;
        v7 = (_QWORD *)*v7;
      }
      goto LABEL_14;
    }
LABEL_15:
    SIPolicyFree(v1);
  }
}

```

## disassembly

```asm
0x18001c9ac  mov     [rsp+arg_0], rbx
0x18001c9b1  mov     [rsp+arg_8], rsi
0x18001c9b6  push    rdi
0x18001c9b7  sub     rsp, 20h
0x18001c9bb  mov     rbx, [rcx]
0x18001c9be  test    rbx, rbx
0x18001c9c1  jz      loc_18001CA65
0x18001c9c7  lea     rsi, [rbx+10h]
0x18001c9cb  mov     qword ptr [rcx], 0
0x18001c9d2  mov     rcx, [rsi]
0x18001c9d5  cmp     rcx, rsi
0x18001c9d8  jz      short loc_18001CA12
0x18001c9da  mov     rdi, [rcx]
0x18001c9dd  mov     rax, rdi
0x18001c9e0  cmp     [rax+8], rcx
0x18001c9e4  jnz     short loc_18001CA56
0x18001c9e6  mov     rdx, [rcx+8]
0x18001c9ea  cmp     [rdx], rcx
0x18001c9ed  jnz     short loc_18001CA56
0x18001c9ef  mov     [rdx], rax
0x18001c9f2  add     rcx, 0FFFFFFFFFFFFFCC0h
0x18001c9f9  mov     [rax+8], rdx
0x18001c9fd  call    SIPolicyUninitialize
0x18001ca02  cmp     rdi, rsi
0x18001ca05  jz      short loc_18001CA12
0x18001ca07  mov     rax, [rdi]
0x18001ca0a  mov     rcx, rdi
0x18001ca0d  mov     rdi, rax
0x18001ca10  jmp     short loc_18001C9E0
0x18001ca12  lea     rsi, [rbx+20h]
0x18001ca16  mov     rcx, [rsi]
0x18001ca19  cmp     rcx, rsi
0x18001ca1c  jz      short loc_18001CA5D
0x18001ca1e  mov     rdi, [rcx]
0x18001ca21  mov     rax, rdi
0x18001ca24  cmp     [rax+8], rcx
0x18001ca28  jnz     short loc_18001CA56
0x18001ca2a  mov     rdx, [rcx+8]
0x18001ca2e  cmp     [rdx], rcx
0x18001ca31  jnz     short loc_18001CA56
0x18001ca33  mov     [rdx], rax
0x18001ca36  add     rcx, 0FFFFFFFFFFFFFCC0h
0x18001ca3d  mov     [rax+8], rdx
0x18001ca41  call    SIPolicyUninitialize
0x18001ca46  cmp     rdi, rsi
0x18001ca49  jz      short loc_18001CA5D
0x18001ca4b  mov     rax, [rdi]
0x18001ca4e  mov     rcx, rdi
0x18001ca51  mov     rdi, rax
0x18001ca54  jmp     short loc_18001CA24
0x18001ca56  mov     ecx, 3
0x18001ca5b  int     29h; Win8: RtlFailFast(ecx)
0x18001ca5d  mov     rcx, rbx
0x18001ca60  call    SIPolicyFree
0x18001ca65  mov     rbx, [rsp+28h+arg_0]
0x18001ca6a  mov     rsi, [rsp+28h+arg_8]
0x18001ca6f  add     rsp, 20h
0x18001ca73  pop     rdi
0x18001ca74  retn
```
