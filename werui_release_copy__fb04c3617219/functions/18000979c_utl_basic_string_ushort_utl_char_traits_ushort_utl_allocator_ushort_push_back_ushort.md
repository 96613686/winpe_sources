# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)

- ea: `0x18000979c`
- end: `0x180009835`
- name: `?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008dfc`
- `0x18000e6a4`
- `0x180010ccc`
- `0x180010df0`
- `0x180011af0`

## callees

- `0x180009498`
- `0x18000977c`
- `0x18000979c`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(
        _QWORD *a1,
        __int16 a2)
{
  char **v2; // rax
  bool v4; // zf
  char *v5; // rcx
  char v7; // di
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r8

  v2 = (char **)(a1 + 2);
  v4 = *a1 == (_QWORD)(a1 + 2);
  v5 = (char *)a1 + 30;
  if ( !v4 )
    v5 = *v2;
  if ( (char *)a1[1] != v5 )
    goto LABEL_8;
  v7 = 0;
  v8 = 2
     * utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(a1)
     + 1;
  if ( v8 > 0x3FFFFFFFFFFFFFF7LL )
    v8 = 0x3FFFFFFFFFFFFFF7LL;
  if ( v9 < v8
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowTo() )
  {
LABEL_8:
    v7 = 1;
    *(_WORD *)a1[1] = a2;
    a1[1] += 2LL;
    *(_WORD *)a1[1] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000979c  mov     [rsp+arg_0], rbx
0x1800097a1  mov     [rsp+arg_8], rsi
0x1800097a6  push    rdi
0x1800097a7  sub     rsp, 20h
0x1800097ab  lea     rax, [rcx+10h]
0x1800097af  mov     rbx, rcx
0x1800097b2  cmp     [rcx], rax
0x1800097b5  lea     r8, [rcx+1Eh]
0x1800097b9  mov     rcx, r8
0x1800097bc  movzx   esi, dx
0x1800097bf  jz      short loc_1800097C4
0x1800097c1  mov     rcx, [rax]
0x1800097c4  cmp     [rbx+8], rcx
0x1800097c8  jnz     short loc_18000980A
0x1800097ca  xor     dil, dil
0x1800097cd  cmp     [rbx], rax
0x1800097d0  jz      short loc_1800097D5
0x1800097d2  mov     r8, [rax]
0x1800097d5  sub     r8, [rbx]
0x1800097d8  mov     rcx, rbx
0x1800097db  sar     r8, 1
0x1800097de  call    ?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)
0x1800097e3  lea     rdx, ds:1[rax*2]
0x1800097eb  mov     rax, 3FFFFFFFFFFFFFF7h
0x1800097f5  cmp     rdx, rax
0x1800097f8  cmova   rdx, rax
0x1800097fc  cmp     r8, rdx
0x1800097ff  jnb     short loc_180009822
0x180009801  call    ?_GrowTo@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowTo(unsigned __int64)
0x180009806  test    al, al
0x180009808  jz      short loc_180009822
0x18000980a  mov     rcx, [rbx+8]
0x18000980e  mov     dil, 1
0x180009811  mov     [rcx], si
0x180009814  add     qword ptr [rbx+8], 2
0x180009819  mov     rdx, [rbx+8]
0x18000981d  xor     ecx, ecx
0x18000981f  mov     [rdx], cx
0x180009822  mov     rbx, [rsp+28h+arg_0]
0x180009827  mov     al, dil
0x18000982a  mov     rsi, [rsp+28h+arg_8]
0x18000982f  add     rsp, 20h
0x180009833  pop     rdi
0x180009834  retn
```
