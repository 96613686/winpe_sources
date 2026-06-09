# CASFScriptCommandObject::Space(void)

- ea: `0x180026200`
- end: `0x18002628b`
- name: `?Space@CASFScriptCommandObject@@UEAAKXZ`
- size: `139`
- prototype: `unsigned int __fastcall(CASFScriptCommandObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026200`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObject::Space(CASFScriptCommandObject *this)
{
  unsigned int v1; // edx
  unsigned int v2; // r8d
  __int64 v3; // r10
  __int64 v4; // rax
  unsigned int v5; // r8d
  __int64 v6; // r10
  __int64 v7; // rax

  v1 = 44;
  if ( *((_WORD *)this + 37) )
  {
    v2 = 0;
    do
    {
      v1 += 2;
      v3 = *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v2);
      if ( v3 )
      {
        v4 = -1;
        do
          ++v4;
        while ( *(_WORD *)(v3 + 2 * v4) );
        v1 += 2 * v4;
      }
      ++v2;
    }
    while ( v2 < *((unsigned __int16 *)this + 37) );
  }
  if ( *((_WORD *)this + 36) )
  {
    v5 = 0;
    do
    {
      v1 += 8;
      v6 = *(_QWORD *)(14LL * v5 + *((_QWORD *)this + 11) + 6);
      if ( v6 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)(v6 + 2 * v7) );
        v1 += 2 * v7;
      }
      ++v5;
    }
    while ( v5 < *((unsigned __int16 *)this + 36) );
  }
  return v1;
}

```

## disassembly

```asm
0x180026200  mov     [rsp+arg_0], rbx
0x180026205  movzx   r9d, word ptr [rcx+4Ah]
0x18002620a  xor     ebx, ebx
0x18002620c  mov     edx, 2Ch ; ','
0x180026211  test    r9d, r9d
0x180026214  jz      short loc_180026245
0x180026216  mov     r11, [rcx+50h]
0x18002621a  mov     r8d, ebx
0x18002621d  mov     eax, r8d
0x180026220  add     edx, 2
0x180026223  mov     r10, [r11+rax*8]
0x180026227  test    r10, r10
0x18002622a  jz      short loc_18002623D
0x18002622c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026230  inc     rax
0x180026233  cmp     [r10+rax*2], bx
0x180026238  jnz     short loc_180026230
0x18002623a  lea     edx, [rdx+rax*2]
0x18002623d  inc     r8d
0x180026240  cmp     r8d, r9d
0x180026243  jb      short loc_18002621D
0x180026245  movzx   r9d, word ptr [rcx+48h]
0x18002624a  test    r9d, r9d
0x18002624d  jz      short loc_180026283
0x18002624f  mov     r11, [rcx+58h]
0x180026253  mov     r8d, ebx
0x180026256  mov     eax, r8d
0x180026259  add     edx, 8
0x18002625c  imul    rcx, rax, 0Eh
0x180026260  mov     r10, [rcx+r11+6]
0x180026265  test    r10, r10
0x180026268  jz      short loc_18002627B
0x18002626a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002626e  inc     rax
0x180026271  cmp     [r10+rax*2], bx
0x180026276  jnz     short loc_18002626E
0x180026278  lea     edx, [rdx+rax*2]
0x18002627b  inc     r8d
0x18002627e  cmp     r8d, r9d
0x180026281  jb      short loc_180026256
0x180026283  mov     rbx, [rsp+arg_0]
0x180026288  mov     eax, edx
0x18002628a  retn
```
