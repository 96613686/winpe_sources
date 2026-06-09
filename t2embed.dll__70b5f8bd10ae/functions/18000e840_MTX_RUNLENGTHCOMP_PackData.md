# MTX_RUNLENGTHCOMP_PackData

- ea: `0x18000e840`
- end: `0x18000e9f2`
- name: `MTX_RUNLENGTHCOMP_PackData`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e2d4`

## callees

- `0x180006400`
- `0x18000e840`
- `0x18001c9ec`
- `0x18002a566`

## pseudocode

```c
_BYTE *__fastcall MTX_RUNLENGTHCOMP_PackData(__int64 a1, __int64 a2, int a3, int *a4)
{
  __int64 i; // rax
  __int64 v8; // rdx
  unsigned int v9; // r8d
  char v10; // r12
  int j; // r9d
  char v12; // cl
  unsigned int v13; // edx
  int v14; // edi
  _BYTE *v15; // r13
  _BYTE *k; // rbx
  int v17; // ecx
  int v18; // ebp
  char v19; // si
  int v20; // ebx
  int v22; // [rsp+20h] [rbp-458h]
  _DWORD v24[258]; // [rsp+30h] [rbp-448h] BYREF

  memset_0(v24, 0, 0x400u);
  for ( i = 0; (int)i < a3; ++v24[v8] )
  {
    v8 = *(unsigned __int8 *)(i + a2);
    i = (unsigned int)(i + 1);
  }
  v9 = v24[0];
  v10 = 0;
  for ( j = 1; j < 256; ++j )
  {
    v12 = j;
    v13 = v24[j];
    if ( v13 >= v9 )
    {
      v12 = v10;
      v13 = v9;
    }
    v10 = v12;
    v9 = v13;
  }
  v22 = v13 + a3 + 1;
  v14 = 0;
  v15 = (_BYTE *)MTX_mem_malloc(*(_QWORD *)(a1 + 8), (unsigned int)v22);
  *v15 = v10;
  for ( k = v15 + 1; v14 < a3; ++k )
  {
    v17 = v14 + 1;
    v18 = 1;
    v19 = *(_BYTE *)(v14 + a2);
    if ( v14 + 1 >= a3 )
      goto LABEL_11;
    do
    {
      if ( v19 != *(_BYTE *)(v17 + a2) )
        break;
      if ( ++v18 >= 255 )
        break;
      ++v17;
    }
    while ( v17 < a3 );
    if ( v18 > 3 )
    {
      if ( v18 > 255 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      *k = v10;
      k[1] = v18;
      k += 2;
      *k = v19;
    }
    else
    {
LABEL_11:
      v18 = 1;
      if ( v19 == v10 )
      {
        *k++ = v10;
        *k = 0;
      }
      else
      {
        *k = v19;
      }
    }
    v14 += v18;
  }
  v20 = (_DWORD)k - (_DWORD)v15;
  *a4 = v20;
  if ( v20 > v22 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return v15;
}

```

## disassembly

```asm
0x18000e840  mov     rax, rsp
0x18000e843  push    r13
0x18000e845  sub     rsp, 470h
0x18000e84c  mov     [rax-10h], rbx
0x18000e850  mov     rbx, rcx
0x18000e853  mov     [rax-28h], rdi
0x18000e857  lea     rcx, [rsp+478h+var_448]; void *
0x18000e85c  mov     [rax-30h], r12
0x18000e860  mov     [rax-38h], r14
0x18000e864  mov     r14d, r8d
0x18000e867  mov     [rax-40h], r15
0x18000e86b  mov     r8d, 400h; Size
0x18000e871  mov     r15, rdx
0x18000e874  mov     [rsp+478h+var_450], r9
0x18000e879  xor     edx, edx; Val
0x18000e87b  call    memset_0
0x18000e880  xor     eax, eax
0x18000e882  test    r14d, r14d
0x18000e885  jle     short loc_18000E8A0
0x18000e887  nop     word ptr [rax+rax+00000000h]
0x18000e890  movzx   edx, byte ptr [rax+r15]
0x18000e895  inc     eax
0x18000e897  inc     [rsp+rdx*4+478h+var_448]
0x18000e89b  cmp     eax, r14d
0x18000e89e  jl      short loc_18000E890
0x18000e8a0  mov     r8d, [rsp+478h+var_448]
0x18000e8a5  xor     r12b, r12b
0x18000e8a8  mov     r9d, 1
0x18000e8ae  mov     eax, r9d
0x18000e8b1  movzx   ecx, r9b
0x18000e8b5  mov     edx, [rsp+rax*4+478h+var_448]
0x18000e8b9  cmp     edx, r8d
0x18000e8bc  movzx   eax, r12b
0x18000e8c0  cmovnb  ecx, eax
0x18000e8c3  cmovnb  edx, r8d
0x18000e8c7  inc     r9d
0x18000e8ca  movzx   r12d, cl
0x18000e8ce  mov     r8d, edx
0x18000e8d1  cmp     r9d, 100h
0x18000e8d8  jl      short loc_18000E8AE
0x18000e8da  mov     rcx, [rbx+8]
0x18000e8de  lea     eax, [r14+1]
0x18000e8e2  add     eax, edx
0x18000e8e4  mov     edx, eax
0x18000e8e6  mov     [rsp+478h+var_458], eax
0x18000e8ea  call    MTX_mem_malloc
0x18000e8ef  xor     edi, edi
0x18000e8f1  mov     r13, rax
0x18000e8f4  mov     [rax], r12b
0x18000e8f7  lea     rbx, [rax+1]
0x18000e8fb  test    r14d, r14d
0x18000e8fe  jle     short loc_18000E95E
0x18000e900  mov     [rsp+478h+var_18], rbp
0x18000e908  mov     [rsp+478h+var_20], rsi
0x18000e910  movsxd  rax, edi
0x18000e913  lea     ecx, [rdi+1]
0x18000e916  mov     ebp, 1
0x18000e91b  movzx   esi, byte ptr [rax+r15]
0x18000e920  cmp     ecx, r14d
0x18000e923  jge     short loc_18000E937
0x18000e925  movsxd  rax, ecx
0x18000e928  cmp     sil, [rax+r15]
0x18000e92c  jz      short loc_18000E9A3
0x18000e92e  cmp     ebp, 3
0x18000e931  jg      loc_18000E9CB
0x18000e937  mov     ebp, 1
0x18000e93c  cmp     sil, r12b
0x18000e93f  jz      short loc_18000E9BD
0x18000e941  mov     [rbx], sil
0x18000e944  add     edi, ebp
0x18000e946  inc     rbx
0x18000e949  cmp     edi, r14d
0x18000e94c  jl      short loc_18000E910
0x18000e94e  mov     rsi, [rsp+478h+var_20]
0x18000e956  mov     rbp, [rsp+478h+var_18]
0x18000e95e  mov     rax, [rsp+478h+var_450]
0x18000e963  sub     ebx, r13d
0x18000e966  cmp     ebx, [rsp+478h+var_458]
0x18000e96a  mov     r15, [rsp+478h+var_40]
0x18000e972  mov     r14, [rsp+478h+var_38]
0x18000e97a  mov     r12, [rsp+478h+var_30]
0x18000e982  mov     rdi, [rsp+478h+var_28]
0x18000e98a  mov     [rax], ebx
0x18000e98c  mov     rbx, [rsp+478h+var_10]
0x18000e994  jg      short loc_18000E9EB
0x18000e996  mov     rax, r13
0x18000e999  add     rsp, 470h
0x18000e9a0  pop     r13
0x18000e9a2  retn
0x18000e9a3  inc     ebp
0x18000e9a5  cmp     ebp, 0FFh
0x18000e9ab  jge     short loc_18000E92E
0x18000e9ad  inc     ecx
0x18000e9af  cmp     ecx, r14d
0x18000e9b2  jge     loc_18000E92E
0x18000e9b8  jmp     loc_18000E925
0x18000e9bd  mov     [rbx], r12b
0x18000e9c0  inc     rbx
0x18000e9c3  mov     byte ptr [rbx], 0
0x18000e9c6  jmp     loc_18000E944
0x18000e9cb  cmp     ebp, 0FFh
0x18000e9d1  jle     short loc_18000E9D8
0x18000e9d3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e9d8  mov     [rbx], r12b
0x18000e9db  mov     [rbx+1], bpl
0x18000e9df  add     rbx, 2
0x18000e9e3  mov     [rbx], sil
0x18000e9e6  jmp     loc_18000E944
0x18000e9eb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e9f0  jmp     short loc_18000E996
```
