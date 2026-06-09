# SlbNatDeleteWildcardStaticMappingsForInstance

- ea: `0x14003179c`
- end: `0x140031854`
- name: `SlbNatDeleteWildcardStaticMappingsForInstance`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140031300`

## callees

- `0x1400310f8`
- `0x1400315a0`
- `0x14003179c`

## pseudocode

```c
void __fastcall SlbNatDeleteWildcardStaticMappingsForInstance(__int64 a1)
{
  PVOID *v1; // rbx
  char *v3; // rcx
  PVOID *v4; // rsi
  PVOID **v5; // rax
  PVOID *v6; // rdi
  PVOID *v7; // rax

  v1 = (PVOID *)qword_140026358;
  if ( qword_140026358 != &qword_140026358 )
  {
    do
    {
      v3 = (char *)v1[2];
      if ( v3 != (char *)(v1 + 2) )
      {
        do
        {
          v4 = *(PVOID **)v3;
          if ( *((_QWORD *)v3 + 16) == *(_QWORD *)(a1 + 288) )
          {
            if ( v4[1] != v3 )
              goto LABEL_15;
            v5 = (PVOID **)*((_QWORD *)v3 + 1);
            if ( *v5 != (PVOID *)v3 )
              goto LABEL_15;
            *v5 = v4;
            v4[1] = v5;
            --*((_DWORD *)v1 + 8);
            SlbNatDeleteStaticMapping(v3, a1);
          }
          v3 = (char *)v4;
        }
        while ( v4 != v1 + 2 );
      }
      v6 = (PVOID *)*v1;
      if ( (*((_BYTE *)v1 + 92) & 1) != 0 && !*((_DWORD *)v1 + 8) )
      {
        if ( v6[1] != v1 || (v7 = (PVOID *)v1[1], *v7 != v1) )
LABEL_15:
          __fastfail(3u);
        *v7 = v6;
        v6[1] = v7;
        SlbNatDeleteExternalAddress((char *)v1, a1);
      }
      v1 = v6;
    }
    while ( v6 != &qword_140026358 );
  }
}

```

## disassembly

```asm
0x14003179c  push    rbx
0x14003179e  push    rbp
0x14003179f  push    rsi
0x1400317a0  push    rdi
0x1400317a1  push    r14
0x1400317a3  sub     rsp, 20h
0x1400317a7  mov     rbx, cs:qword_140026358
0x1400317ae  lea     r14, qword_140026358
0x1400317b5  mov     rbp, rcx
0x1400317b8  cmp     rbx, r14
0x1400317bb  jz      loc_140031841
0x1400317c1  lea     rdi, [rbx+10h]
0x1400317c5  mov     rcx, [rdi]; P
0x1400317c8  cmp     rcx, rdi
0x1400317cb  jz      short loc_140031809
0x1400317cd  mov     rax, [rbp+120h]
0x1400317d4  mov     rsi, [rcx]
0x1400317d7  cmp     [rcx+80h], rax
0x1400317de  jnz     short loc_140031801
0x1400317e0  cmp     [rsi+8], rcx
0x1400317e4  jnz     short loc_14003184D
0x1400317e6  mov     rax, [rcx+8]
0x1400317ea  cmp     [rax], rcx
0x1400317ed  jnz     short loc_14003184D
0x1400317ef  mov     [rax], rsi
0x1400317f2  mov     rdx, rbp
0x1400317f5  mov     [rsi+8], rax
0x1400317f9  dec     dword ptr [rbx+20h]
0x1400317fc  call    SlbNatDeleteStaticMapping
0x140031801  mov     rcx, rsi
0x140031804  cmp     rsi, rdi
0x140031807  jnz     short loc_1400317CD
0x140031809  test    byte ptr [rbx+5Ch], 1
0x14003180d  mov     rdi, [rbx]
0x140031810  jz      short loc_140031839
0x140031812  cmp     dword ptr [rbx+20h], 0
0x140031816  jnz     short loc_140031839
0x140031818  cmp     [rdi+8], rbx
0x14003181c  jnz     short loc_14003184D
0x14003181e  mov     rax, [rbx+8]
0x140031822  cmp     [rax], rbx
0x140031825  jnz     short loc_14003184D
0x140031827  mov     [rax], rdi
0x14003182a  mov     rdx, rbp
0x14003182d  mov     rcx, rbx; P
0x140031830  mov     [rdi+8], rax
0x140031834  call    SlbNatDeleteExternalAddress
0x140031839  mov     rbx, rdi
0x14003183c  cmp     rdi, r14
0x14003183f  jnz     short loc_1400317C1
0x140031841  add     rsp, 20h
0x140031845  pop     r14
0x140031847  pop     rdi
0x140031848  pop     rsi
0x140031849  pop     rbp
0x14003184a  pop     rbx
0x14003184b  retn
0x14003184d  mov     ecx, 3
0x140031852  int     29h; Win8: RtlFailFast(ecx)
```
