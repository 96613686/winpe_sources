# WdipReadScenarioInstanceFromMessageBuffer(__WDIP_QUEUED_RESOLUTION *,_DPS_MESSAGE *,uchar * *,uchar * *,uchar *)

- ea: `0x18000dfc4`
- end: `0x18000e290`
- name: `?WdipReadScenarioInstanceFromMessageBuffer@@YAJPEAU__WDIP_QUEUED_RESOLUTION@@PEAU_DPS_MESSAGE@@PEAPEAE2PEAE@Z`
- size: `716`
- prototype: `__int64 __fastcall(struct __WDIP_QUEUED_RESOLUTION *, struct _DPS_MESSAGE *, unsigned int **, char **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e298`

## callees

- `0x180002ba0`
- `0x18000dfc4`
- `0x18000f1b6`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e04f`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e067`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e098`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e0b7`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e04f`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e067`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e098`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000e0b7`

## string_xrefs

- `0x18000dffe`: `WdipReadScenarioInstanceFromMessageBuffer`
- `0x18000e265`: `WdipReadScenarioInstanceFromMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipReadScenarioInstanceFromMessageBuffer(
        struct __WDIP_QUEUED_RESOLUTION *a1,
        struct _DPS_MESSAGE *a2,
        unsigned int **a3,
        char **a4,
        unsigned __int8 *a5)
{
  int v9; // r8d
  unsigned int v10; // ebx
  unsigned int *v11; // rdi
  char *v12; // r13
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // r12
  int v15; // r8d
  size_t v16; // r12
  size_t v17; // rdi
  char *v18; // rsi
  char *v19; // rcx
  char *v20; // r13
  unsigned __int8 *v21; // rax
  size_t v22; // rsi
  char *v23; // rcx
  unsigned __int8 *v24; // rbx
  size_t v25; // r13
  unsigned int v27; // [rsp+30h] [rbp-58h]
  unsigned int *v28; // [rsp+90h] [rbp+8h]
  char *v29; // [rsp+90h] [rbp+8h]
  char *v30; // [rsp+90h] [rbp+8h]

  if ( !a1 )
  {
    v9 = 60;
LABEL_3:
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdierc.cpp",
      (int)L"WdipReadScenarioInstanceFromMessageBuffer",
      v9,
      (int)L"Error = %d",
      87);
    return v10;
  }
  if ( !a2 )
  {
    v9 = 61;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v9 = 62;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v9 = 63;
    goto LABEL_3;
  }
  v11 = *a3;
  if ( !*a3
    || v11 < (unsigned int *)a2
    || (v12 = *a4, (char *)v11 - (char *)a2 > (unsigned __int64)AlpcMaxAllowedMessageLength())
    || (unsigned __int64)(a2 - (struct _DPS_MESSAGE *)v11 + AlpcMaxAllowedMessageLength()) < 4 )
  {
    v15 = 75;
    goto LABEL_30;
  }
  v13 = (unsigned __int64)*a3;
  if ( !*a3
    || v13 < (unsigned __int64)a2
    || (v14 = *v11, v27 = *v11, v13 - (unsigned __int64)a2 > AlpcMaxAllowedMessageLength())
    || v14 > (unsigned __int64)a2 + AlpcMaxAllowedMessageLength() - v13 )
  {
    v15 = 90;
LABEL_30:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdierc.cpp",
      (int)L"WdipReadScenarioInstanceFromMessageBuffer",
      v15,
      (int)L"Error = %d",
      111);
    return (unsigned int)-2147024362;
  }
  *(_OWORD *)a1 = *(_OWORD *)(v11 + 1);
  *((_OWORD *)a1 + 1) = *(_OWORD *)(v11 + 5);
  *((_OWORD *)a1 + 2) = *(_OWORD *)(v11 + 9);
  *((_QWORD *)a1 + 6) = *(_QWORD *)(v11 + 13);
  *((_QWORD *)a1 + 7) = *(_QWORD *)(v11 + 15);
  *((_DWORD *)a1 + 16) = v11[17];
  *((_DWORD *)a1 + 17) = v11[18];
  v16 = v11[19];
  if ( v16 <= a5 - (unsigned __int8 *)v12 )
  {
    *((_QWORD *)a1 + 9) = v12;
    v28 = v11 + 20;
    memcpy_0(v12, v11 + 20, v16);
    v17 = *(unsigned int *)((char *)v11 + v16 + 80);
    v18 = &v12[v16];
    if ( v17 <= a5 - (unsigned __int8 *)&v12[v16] )
    {
      *((_QWORD *)a1 + 10) = v18;
      v29 = (char *)v28 + v16 + 4;
      memcpy_0(&v12[v16], v29, v17);
      v19 = v29;
      v20 = &v18[v17];
      v21 = (unsigned __int8 *)(a5 - (unsigned __int8 *)&v18[v17]);
      v22 = *(unsigned int *)&v29[v17];
      if ( v22 <= (unsigned __int64)v21 )
      {
        *((_QWORD *)a1 + 11) = v20;
        v30 = &v29[v17 + 4];
        memcpy_0(v20, &v19[v17 + 4], v22);
        v23 = &v20[v22];
        v24 = (unsigned __int8 *)(a5 - (unsigned __int8 *)&v20[v22]);
        v25 = *(unsigned int *)&v30[v22];
        if ( v25 <= (unsigned __int64)v24 )
        {
          *((_QWORD *)a1 + 12) = v23;
          v10 = 0;
          memcpy_0(v23, &v30[v22 + 4], v25);
          *a3 = (unsigned int *)((char *)*a3 + v27);
          *a4 += (unsigned int)(v16 + v17 + v22 + v25);
        }
        else
        {
          v10 = -2147024785;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdierc.cpp",
            (int)L"WdipReadScenarioInstanceFromMessageBuffer",
            202,
            (int)L"Error = %d",
            111);
        }
      }
      else
      {
        v10 = -2147024785;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdierc.cpp",
          (int)L"WdipReadScenarioInstanceFromMessageBuffer",
          184,
          (int)L"Error = %d",
          111);
      }
    }
    else
    {
      v10 = -2147024785;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdierc.cpp",
        (int)L"WdipReadScenarioInstanceFromMessageBuffer",
        166,
        (int)L"Error = %d",
        111);
    }
  }
  else
  {
    v10 = -2147024785;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdierc.cpp",
      (int)L"WdipReadScenarioInstanceFromMessageBuffer",
      148,
      (int)L"Error = %d",
      111);
  }
  return v10;
}

```

## disassembly

```asm
0x18000dfc4  push    rbx
0x18000dfc6  push    rbp
0x18000dfc7  push    rsi
0x18000dfc8  push    rdi
0x18000dfc9  push    r12
0x18000dfcb  push    r13
0x18000dfcd  push    r14
0x18000dfcf  push    r15
0x18000dfd1  sub     rsp, 48h
0x18000dfd5  mov     r15, r9
0x18000dfd8  mov     r14, r8
0x18000dfdb  mov     rbx, rdx
0x18000dfde  mov     rbp, rcx
0x18000dfe1  test    rcx, rcx
0x18000dfe4  jnz     short loc_18000E016
0x18000dfe6  lea     r8d, [rcx+3Ch]; int
0x18000dfea  mov     dword ptr [rsp+88h+Args], 57h ; 'W'; Args
0x18000dff2  mov     ebx, 80070057h
0x18000dff7  lea     r9, aErrorD_0; "Error = %d"
0x18000dffe  lea     rdx, aWdipreadscenar; "WdipReadScenarioInstanceFromMessageBuff"...
0x18000e005  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000e00c  call    WdipTraceError
0x18000e011  jmp     loc_18000E27D
0x18000e016  test    rbx, rbx
0x18000e019  jnz     short loc_18000E021
0x18000e01b  lea     r8d, [rbx+3Dh]
0x18000e01f  jmp     short loc_18000DFEA
0x18000e021  test    r14, r14
0x18000e024  jnz     short loc_18000E02C
0x18000e026  lea     r8d, [r14+3Eh]
0x18000e02a  jmp     short loc_18000DFEA
0x18000e02c  test    r15, r15
0x18000e02f  jnz     short loc_18000E037
0x18000e031  lea     r8d, [r15+3Fh]
0x18000e035  jmp     short loc_18000DFEA
0x18000e037  mov     rdi, [r8]
0x18000e03a  test    rdi, rdi
0x18000e03d  jz      loc_18000E250
0x18000e043  cmp     rdi, rbx
0x18000e046  jb      loc_18000E250
0x18000e04c  mov     r13, [r9]
0x18000e04f  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000e055  mov     rcx, rax
0x18000e058  mov     rax, rdi
0x18000e05b  sub     rax, rbx
0x18000e05e  cmp     rax, rcx
0x18000e061  ja      loc_18000E250
0x18000e067  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000e06d  mov     rcx, rax
0x18000e070  mov     rax, rbx
0x18000e073  sub     rax, rdi
0x18000e076  add     rcx, rax
0x18000e079  cmp     rcx, 4
0x18000e07d  jb      loc_18000E250
0x18000e083  mov     rsi, [r14]
0x18000e086  test    rsi, rsi
0x18000e089  jz      short loc_18000E0AC
0x18000e08b  cmp     rsi, rbx
0x18000e08e  jb      short loc_18000E0AC
0x18000e090  mov     r12d, [rdi]
0x18000e093  mov     qword ptr [rsp+88h+var_58], r12
0x18000e098  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000e09e  mov     rcx, rax
0x18000e0a1  mov     rax, rsi
0x18000e0a4  sub     rax, rbx
0x18000e0a7  cmp     rax, rcx
0x18000e0aa  jbe     short loc_18000E0B7
0x18000e0ac  mov     r8d, 5Ah ; 'Z'
0x18000e0b2  jmp     loc_18000E256
0x18000e0b7  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18000e0bd  sub     rbx, rsi
0x18000e0c0  add     rax, rbx
0x18000e0c3  cmp     r12, rax
0x18000e0c6  ja      short loc_18000E0AC
0x18000e0c8  movups  xmm0, xmmword ptr [rdi+4]
0x18000e0cc  mov     rbx, [rsp+88h+arg_20]
0x18000e0d4  movdqu  xmmword ptr [rbp+0], xmm0
0x18000e0d9  movups  xmm0, xmmword ptr [rdi+14h]
0x18000e0dd  movdqu  xmmword ptr [rbp+10h], xmm0
0x18000e0e2  movups  xmm1, xmmword ptr [rdi+24h]
0x18000e0e6  movdqu  xmmword ptr [rbp+20h], xmm1
0x18000e0eb  mov     rax, [rdi+34h]
0x18000e0ef  mov     [rbp+30h], rax
0x18000e0f3  mov     rax, [rdi+3Ch]
0x18000e0f7  mov     [rbp+38h], rax
0x18000e0fb  mov     eax, [rdi+44h]
0x18000e0fe  mov     [rbp+40h], eax
0x18000e101  mov     eax, [rdi+48h]
0x18000e104  mov     [rbp+44h], eax
0x18000e107  mov     rax, rbx
0x18000e10a  mov     r12d, [rdi+4Ch]
0x18000e10e  sub     rax, r13
0x18000e111  cmp     r12, rax
0x18000e114  jbe     short loc_18000E12E
0x18000e116  mov     ebx, 8007006Fh
0x18000e11b  mov     dword ptr [rsp+88h+Args], 6Fh ; 'o'
0x18000e123  mov     r8d, 94h
0x18000e129  jmp     loc_18000DFF7
0x18000e12e  add     rdi, 50h ; 'P'
0x18000e132  mov     [rbp+48h], r13
0x18000e136  mov     rdx, rdi; Src
0x18000e139  mov     [rsp+88h+arg_0], rdi
0x18000e141  mov     r8, r12; Size
0x18000e144  mov     rcx, r13; void *
0x18000e147  call    memcpy_0
0x18000e14c  mov     edi, [r12+rdi]
0x18000e150  lea     rsi, [r12+r13]
0x18000e154  mov     rax, rbx
0x18000e157  sub     rax, rsi
0x18000e15a  cmp     rdi, rax
0x18000e15d  jbe     short loc_18000E177
0x18000e15f  mov     ebx, 8007006Fh
0x18000e164  mov     dword ptr [rsp+88h+Args], 6Fh ; 'o'
0x18000e16c  mov     r8d, 0A6h
0x18000e172  jmp     loc_18000DFF7
0x18000e177  mov     rax, [rsp+88h+arg_0]
0x18000e17f  mov     r8, rdi; Size
0x18000e182  add     rax, 4
0x18000e186  mov     [rbp+50h], rsi
0x18000e18a  add     rax, r12
0x18000e18d  mov     rcx, rsi; void *
0x18000e190  mov     rdx, rax; Src
0x18000e193  mov     [rsp+88h+arg_0], rax
0x18000e19b  call    memcpy_0
0x18000e1a0  mov     rcx, [rsp+88h+arg_0]
0x18000e1a8  lea     r13, [rdi+rsi]
0x18000e1ac  mov     rax, rbx
0x18000e1af  sub     rax, r13
0x18000e1b2  mov     esi, [rdi+rcx]
0x18000e1b5  cmp     rsi, rax
0x18000e1b8  jbe     short loc_18000E1D2
0x18000e1ba  mov     ebx, 8007006Fh
0x18000e1bf  mov     dword ptr [rsp+88h+Args], 6Fh ; 'o'
0x18000e1c7  mov     r8d, 0B8h
0x18000e1cd  jmp     loc_18000DFF7
0x18000e1d2  lea     rax, [rcx+4]
0x18000e1d6  mov     [rbp+58h], r13
0x18000e1da  add     rax, rdi
0x18000e1dd  mov     r8, rsi; Size
0x18000e1e0  mov     rdx, rax; Src
0x18000e1e3  mov     [rsp+88h+arg_0], rax
0x18000e1eb  mov     rcx, r13; void *
0x18000e1ee  call    memcpy_0
0x18000e1f3  mov     rax, [rsp+88h+arg_0]
0x18000e1fb  lea     rcx, [rsi+r13]; void *
0x18000e1ff  sub     rbx, rcx
0x18000e202  mov     r13d, [rsi+rax]
0x18000e206  cmp     r13, rbx
0x18000e209  jbe     short loc_18000E223
0x18000e20b  mov     ebx, 8007006Fh
0x18000e210  mov     dword ptr [rsp+88h+Args], 6Fh ; 'o'
0x18000e218  mov     r8d, 0CAh
0x18000e21e  jmp     loc_18000DFF7
0x18000e223  lea     rdx, [rax+4]
0x18000e227  mov     [rbp+60h], rcx
0x18000e22b  add     rdx, rsi; Src
0x18000e22e  mov     r8, r13; Size
0x18000e231  xor     ebx, ebx
0x18000e233  call    memcpy_0
0x18000e238  mov     rax, qword ptr [rsp+88h+var_58]
0x18000e23d  mov     eax, eax
0x18000e23f  add     [r14], rax
0x18000e242  lea     eax, [rsi+r13]
0x18000e246  add     eax, edi
0x18000e248  add     eax, r12d
0x18000e24b  add     [r15], rax
0x18000e24e  jmp     short loc_18000E27D
0x18000e250  mov     r8d, 4Bh ; 'K'; int
0x18000e256  lea     r9, aErrorD_0; "Error = %d"
0x18000e25d  mov     dword ptr [rsp+88h+Args], 6Fh ; 'o'; Args
0x18000e265  lea     rdx, aWdipreadscenar; "WdipReadScenarioInstanceFromMessageBuff"...
0x18000e26c  lea     rcx, aClientcoreBase_10; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000e273  call    WdipTraceError
0x18000e278  mov     ebx, 80070216h
0x18000e27d  mov     eax, ebx
0x18000e27f  add     rsp, 48h
0x18000e283  pop     r15
0x18000e285  pop     r14
0x18000e287  pop     r13
0x18000e289  pop     r12
0x18000e28b  pop     rdi
0x18000e28c  pop     rsi
0x18000e28d  pop     rbp
0x18000e28e  pop     rbx
0x18000e28f  retn
```
