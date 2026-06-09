# CSrmDebugInfo::operator<<(ushort const *)

- ea: `0x180016830`
- end: `0x180016a16`
- name: `??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z`
- size: `486`
- prototype: `CSrmDebugInfo *__fastcall(struct CSrmDebugInfo *, CSrmDebugInfo *this, __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800166ec`
- `0x1800198e0`

## callees

- `0x180016170`
- `0x180016830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800168d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800168d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016980`

## pseudocode

```c
CSrmDebugInfo *__fastcall CSrmDebugInfo::operator<<(struct CSrmDebugInfo *a1, CSrmDebugInfo *this, __int16 *a3)
{
  __int16 *v3; // r15
  __int64 v6; // rbp
  __int64 v7; // r12
  unsigned __int16 i; // r12
  __int64 v9; // rax
  __int64 v10; // r14
  unsigned __int64 v11; // r14
  _WORD *v12; // rax
  _WORD *v13; // r9
  __int64 v14; // rdx
  __int16 *v15; // r8
  __int16 v16; // cx
  _WORD *v17; // rcx
  unsigned __int64 v18; // r14
  _WORD *v19; // rax
  _WORD *v20; // rdx
  __int16 v21; // cx
  _WORD *v22; // rcx

  v3 = a3;
  if ( a3 )
  {
    if ( !*((_BYTE *)a1 + 138) )
    {
      v6 = -1;
      v7 = 2147483646;
      if ( !*((_BYTE *)a1 + 139) )
      {
        *((_BYTE *)a1 + 139) = 1;
        for ( i = 0; i < *((_WORD *)a1 + 68); ++i )
        {
          v9 = *((_QWORD *)a1 + i + 5);
          if ( v9 )
          {
            v10 = -1;
            do
              ++v10;
            while ( *(_WORD *)(v9 + 2 * v10) );
            v11 = v10 + 1;
            v12 = CoTaskMemAlloc(2 * v11);
            v13 = v12;
            if ( !v12 )
              goto LABEL_30;
            if ( v11 )
            {
              if ( v11 <= 0x7FFFFFFF )
              {
                v14 = 2147483646;
                v15 = (__int16 *)*((_QWORD *)a1 + i + 5);
                do
                {
                  if ( !v14 )
                    break;
                  v16 = *v15;
                  if ( !*v15 )
                    break;
                  ++v15;
                  *v12++ = v16;
                  --v14;
                  --v11;
                }
                while ( v11 );
                v17 = v12 - 1;
                if ( v11 )
                  v17 = v12;
                *v17 = 0;
              }
              else
              {
                *v12 = 0;
              }
            }
            *((_QWORD *)a1 + i + 5) = v13;
          }
        }
        v7 = 2147483646;
      }
      if ( *((_BYTE *)a1 + 139) && *((_WORD *)a1 + 68) < 0xCu )
      {
        do
          ++v6;
        while ( v3[v6] );
        v18 = v6 + 1;
        v19 = CoTaskMemAlloc(2 * (v6 + 1));
        v20 = v19;
        if ( v19 )
        {
          if ( v6 != -1 )
          {
            if ( v18 <= 0x7FFFFFFF )
            {
              do
              {
                if ( !v7 )
                  break;
                v21 = *v3;
                if ( !*v3 )
                  break;
                ++v3;
                *v19++ = v21;
                --v7;
                --v18;
              }
              while ( v18 );
              v22 = v19 - 1;
              if ( v18 )
                v22 = v19;
              *v22 = 0;
            }
            else
            {
              *v19 = 0;
            }
          }
          *((_QWORD *)a1 + (unsigned __int16)(*((_WORD *)a1 + 68))++ + 5) = v20;
        }
        else
        {
LABEL_30:
          *((_BYTE *)a1 + 138) = 1;
        }
      }
    }
    CSrmDebugInfo::CSrmDebugInfo(this, a1);
  }
  else
  {
    CSrmDebugInfo::CSrmDebugInfo(this, a1);
  }
  return this;
}

```

## disassembly

```asm
0x180016830  mov     [rsp+arg_8], rdx
0x180016835  push    rbx
0x180016836  push    rbp
0x180016837  push    rsi
0x180016838  push    rdi
0x180016839  push    r12
0x18001683b  push    r13
0x18001683d  push    r14
0x18001683f  push    r15
0x180016841  sub     rsp, 38h
0x180016845  mov     r15, r8
0x180016848  mov     rsi, rdx
0x18001684b  mov     rbx, rcx
0x18001684e  xor     r10d, r10d
0x180016851  mov     [rsp+78h+var_58], r10d
0x180016856  test    r8, r8
0x180016859  jnz     short loc_180016870
0x18001685b  mov     rdx, rcx; struct CSrmDebugInfo *
0x18001685e  mov     rcx, rsi; this
0x180016861  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180016866  nop
0x180016867  lea     edi, [r15+1]
0x18001686b  jmp     loc_1800169FD
0x180016870  mov     edi, 1
0x180016875  cmp     [rcx+8Ah], r10b
0x18001687c  jnz     loc_1800169F1
0x180016882  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180016886  mov     r12d, 7FFFFFFEh
0x18001688c  cmp     [rcx+8Bh], r10b
0x180016893  jnz     loc_180016953
0x180016899  mov     [rcx+8Bh], dil
0x1800168a0  mov     r12d, r10d
0x1800168a3  cmp     r10w, [rcx+88h]
0x1800168ab  jnb     loc_18001694D
0x1800168b1  movzx   r13d, r12w
0x1800168b5  mov     rax, [rbx+r13*8+28h]
0x1800168ba  test    rax, rax
0x1800168bd  jz      short loc_18001693B
0x1800168bf  mov     r14, rbp
0x1800168c2  inc     r14
0x1800168c5  cmp     [rax+r14*2], r10w
0x1800168ca  jnz     short loc_1800168C2
0x1800168cc  inc     r14
0x1800168cf  lea     rcx, [r14+r14]; cb
0x1800168d3  call    cs:__imp_CoTaskMemAlloc
0x1800168d9  mov     r9, rax
0x1800168dc  xor     r10d, r10d
0x1800168df  test    rax, rax
0x1800168e2  jz      loc_1800169A5
0x1800168e8  test    r14, r14
0x1800168eb  jz      short loc_180016936
0x1800168ed  cmp     r14, 7FFFFFFFh
0x1800168f4  jbe     short loc_1800168FC
0x1800168f6  mov     [rax], r10w
0x1800168fa  jmp     short loc_180016936
0x1800168fc  mov     edx, 7FFFFFFEh
0x180016901  mov     r8, [rbx+r13*8+28h]
0x180016906  test    rdx, rdx
0x180016909  jz      short loc_180016927
0x18001690b  movzx   ecx, word ptr [r8]
0x18001690f  test    cx, cx
0x180016912  jz      short loc_180016927
0x180016914  add     r8, 2
0x180016918  mov     [rax], cx
0x18001691b  add     rax, 2
0x18001691f  sub     rdx, rdi
0x180016922  sub     r14, rdi
0x180016925  jnz     short loc_180016906
0x180016927  lea     rcx, [rax-2]
0x18001692b  test    r14, r14
0x18001692e  cmovnz  rcx, rax
0x180016932  mov     [rcx], r10w
0x180016936  mov     [rbx+r13*8+28h], r9
0x18001693b  add     r12w, di
0x18001693f  cmp     r12w, [rbx+88h]
0x180016947  jb      loc_1800168B1
0x18001694d  mov     r12d, 7FFFFFFEh
0x180016953  cmp     [rbx+8Bh], r10b
0x18001695a  jz      loc_1800169F1
0x180016960  cmp     word ptr [rbx+88h], 0Ch
0x180016968  jnb     loc_1800169F1
0x18001696e  inc     rbp
0x180016971  cmp     [r15+rbp*2], r10w
0x180016976  jnz     short loc_18001696E
0x180016978  lea     r14, [rbp+1]
0x18001697c  lea     rcx, [r14+r14]; cb
0x180016980  call    cs:__imp_CoTaskMemAlloc
0x180016986  mov     rdx, rax
0x180016989  xor     r8d, r8d
0x18001698c  test    rax, rax
0x18001698f  jz      short loc_1800169A5
0x180016991  test    r14, r14
0x180016994  jz      short loc_1800169DE
0x180016996  cmp     r14, 7FFFFFFFh
0x18001699d  jbe     short loc_1800169AE
0x18001699f  mov     [rax], r8w
0x1800169a3  jmp     short loc_1800169DE
0x1800169a5  mov     [rbx+8Ah], dil
0x1800169ac  jmp     short loc_1800169F1
0x1800169ae  test    r12, r12
0x1800169b1  jz      short loc_1800169CF
0x1800169b3  movzx   ecx, word ptr [r15]
0x1800169b7  test    cx, cx
0x1800169ba  jz      short loc_1800169CF
0x1800169bc  add     r15, 2
0x1800169c0  mov     [rax], cx
0x1800169c3  add     rax, 2
0x1800169c7  sub     r12, rdi
0x1800169ca  sub     r14, rdi
0x1800169cd  jnz     short loc_1800169AE
0x1800169cf  lea     rcx, [rax-2]
0x1800169d3  test    r14, r14
0x1800169d6  cmovnz  rcx, rax
0x1800169da  mov     [rcx], r8w
0x1800169de  movzx   eax, word ptr [rbx+88h]
0x1800169e5  mov     [rbx+rax*8+28h], rdx
0x1800169ea  add     [rbx+88h], di
0x1800169f1  mov     rdx, rbx; struct CSrmDebugInfo *
0x1800169f4  mov     rcx, rsi; this
0x1800169f7  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x1800169fc  nop
0x1800169fd  mov     [rsp+78h+var_58], edi
0x180016a01  mov     rax, rsi
0x180016a04  add     rsp, 38h
0x180016a08  pop     r15
0x180016a0a  pop     r14
0x180016a0c  pop     r13
0x180016a0e  pop     r12
0x180016a10  pop     rdi
0x180016a11  pop     rsi
0x180016a12  pop     rbp
0x180016a13  pop     rbx
0x180016a14  retn
```
