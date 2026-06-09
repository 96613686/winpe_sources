# WdipReadParameterFromMessageBuffer(_DPS_MESSAGE *,unsigned __int64,uchar * *)

- ea: `0x18000e9e0`
- end: `0x18000ed4f`
- name: `?WdipReadParameterFromMessageBuffer@@YAPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@_KPEAPEAE@Z`
- size: `879`
- prototype: `struct __WDIP_PARAMETER *__fastcall(struct _DPS_MESSAGE *, unsigned __int64, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007b00`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180007900`
- `0x18000e9e0`
- `0x18000f1b6`
- `0x18000f1c2`

## string_xrefs

- `0x18000ea29`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000ed07`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000ea22`: `WdipReadParameterFromMessageBuffer`
- `0x18000ed0e`: `WdipReadParameterFromMessageBuffer`

## pseudocode

```c
struct __WDIP_PARAMETER *__fastcall WdipReadParameterFromMessageBuffer(
        struct _DPS_MESSAGE *a1,
        unsigned __int64 a2,
        unsigned __int8 **a3)
{
  __int64 v3; // r14
  int v7; // r8d
  __int64 v8; // rax
  __int64 v9; // rbp
  int v10; // r8d
  char Args; // al
  struct _DPS_MESSAGE *v12; // rcx
  signed __int64 v13; // rdx
  char *v14; // r9
  __int128 v15; // xmm0
  struct _DPS_MESSAGE *v16; // r8
  __int128 v17; // xmm0
  struct _DPS_MESSAGE *v18; // r8
  int v19; // eax
  struct _DPS_MESSAGE *v20; // r8
  int v21; // eax
  struct _DPS_MESSAGE *v22; // r8
  int v23; // eax
  bool v24; // zf
  unsigned __int8 *v25; // rcx
  size_t v26; // r14
  unsigned int v27; // eax
  size_t v28; // r15
  void *v29; // rax
  unsigned __int64 v30; // r15
  unsigned int *v31; // rdx
  __int64 v32; // rcx
  void *v33; // rax
  size_t v34; // r8
  __int64 v36; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  if ( !*a3 )
  {
    v7 = 171;
LABEL_3:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterFromMessageBuffer",
      v7,
      (int)L"Error = %d",
      87);
    return (struct __WDIP_PARAMETER *)v3;
  }
  if ( !a1 )
  {
    v7 = 172;
    goto LABEL_3;
  }
  v8 = WdipAlloc(64);
  v36 = v8;
  v9 = v8;
  if ( !v8 )
  {
    v10 = 175;
    Args = 14;
    goto LABEL_64;
  }
  v12 = (struct _DPS_MESSAGE *)*a3;
  *(_QWORD *)(v8 + 48) = 0;
  *(_QWORD *)(v8 + 56) = 0;
  if ( v12
    && v12 >= a1
    && (v13 = v12 - a1, v12 - a1 <= a2)
    && (v14 = (char *)(a2 + a1 - v12), (unsigned __int64)v14 >= 0x10) )
  {
    v15 = *(_OWORD *)v12;
    v16 = (struct _DPS_MESSAGE *)((char *)v12 + 16);
    *a3 = (unsigned __int8 *)v12 + 16;
    *(_OWORD *)v8 = v15;
    if ( v12 == (struct _DPS_MESSAGE *)-16LL || v16 < a1 || v13 + 16 > a2 || (unsigned __int64)(v14 - 16) < 0x10 )
    {
      v10 = 195;
    }
    else
    {
      v17 = *(_OWORD *)v16;
      v18 = (struct _DPS_MESSAGE *)((char *)v12 + 32);
      *a3 = (unsigned __int8 *)v12 + 32;
      *(_OWORD *)(v8 + 16) = v17;
      if ( v12 == (struct _DPS_MESSAGE *)-32LL || v18 < a1 || v13 + 32 > a2 || (unsigned __int64)(v14 - 32) < 4 )
      {
        v10 = 206;
      }
      else
      {
        v19 = *(_DWORD *)v18;
        v20 = (struct _DPS_MESSAGE *)((char *)v12 + 36);
        *(_DWORD *)(v9 + 32) = v19;
        *a3 = (unsigned __int8 *)v12 + 36;
        if ( v12 == (struct _DPS_MESSAGE *)-36LL || v20 < a1 || v13 + 36 > a2 || (unsigned __int64)(v14 - 36) < 4 )
        {
          v10 = 217;
        }
        else
        {
          v21 = *(_DWORD *)v20;
          v22 = (struct _DPS_MESSAGE *)((char *)v12 + 40);
          *(_DWORD *)(v9 + 36) = v21;
          *a3 = (unsigned __int8 *)v12 + 40;
          if ( v12 == (struct _DPS_MESSAGE *)-40LL || v22 < a1 || v13 + 40 > a2 || (unsigned __int64)(v14 - 40) < 4 )
          {
            v10 = 228;
          }
          else
          {
            v23 = *(_DWORD *)v22;
            v24 = (struct _DPS_MESSAGE *)((char *)v12 + 44) == 0;
            v25 = (unsigned __int8 *)v12 + 44;
            *a3 = v25;
            *(_DWORD *)(v9 + 44) = v23;
            if ( v24
              || v25 < (unsigned __int8 *)a1
              || v25 - (unsigned __int8 *)a1 > a2
              || a2 + a1 - (struct _DPS_MESSAGE *)v25 < 4 )
            {
              v10 = 239;
            }
            else
            {
              v26 = *(unsigned int *)v25;
              *a3 = v25 + 4;
              v27 = v26 + 2;
              if ( (int)v26 + 2 < (unsigned int)v26 )
              {
                v10 = 255;
                Args = 22;
LABEL_39:
                v3 = 0;
                goto LABEL_64;
              }
              v28 = v27;
              v29 = (void *)WdipAlloc(v27);
              *(_QWORD *)(v9 + 48) = v29;
              if ( !v29 )
              {
                v10 = 258;
LABEL_42:
                Args = 14;
                goto LABEL_39;
              }
              memset_0(v29, 0, v28);
              v30 = (unsigned __int64)*a3;
              if ( *a3
                && v30 >= (unsigned __int64)a1
                && v30 - (unsigned __int64)a1 <= a2
                && v26 <= (unsigned __int64)a1 + a2 - v30 )
              {
                memcpy_0(*(void **)(v9 + 48), *a3, v26);
                v31 = (unsigned int *)(v30 + v26);
                *a3 = (unsigned __int8 *)(v30 + v26);
                if ( v30 + v26
                  && v31 >= (unsigned int *)a1
                  && v30 - (_QWORD)a1 + v26 <= a2
                  && (unsigned __int64)a1 + a2 - v26 - v30 >= 4 )
                {
                  v32 = *v31;
                  *(_DWORD *)(v9 + 40) = v32;
                  *a3 = (unsigned __int8 *)(v31 + 1);
                  v33 = (void *)WdipAlloc(v32);
                  *(_QWORD *)(v9 + 56) = v33;
                  if ( !v33 )
                  {
                    v10 = 284;
                    goto LABEL_42;
                  }
                  if ( *a3 )
                  {
                    if ( *a3 >= (unsigned __int8 *)a1 && *a3 - (unsigned __int8 *)a1 <= a2 )
                    {
                      v34 = *(unsigned int *)(v9 + 40);
                      if ( v34 <= a2 + a1 - (struct _DPS_MESSAGE *)*a3 )
                      {
                        memcpy_0(v33, *a3, v34);
                        v3 = v9;
                        *a3 += *(unsigned int *)(v9 + 40);
                        return (struct __WDIP_PARAMETER *)v3;
                      }
                    }
                  }
                  v10 = 290;
                }
                else
                {
                  v10 = 276;
                }
              }
              else
              {
                v10 = 265;
              }
              v3 = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v10 = 184;
  }
  Args = 111;
LABEL_64:
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
    (int)L"WdipReadParameterFromMessageBuffer",
    v10,
    (int)L"Error = %d",
    Args);
  if ( v9 )
    WdipDeleteParameter(&v36);
  return (struct __WDIP_PARAMETER *)v3;
}

```

## disassembly

```asm
0x18000e9e0  mov     [rsp+arg_0], rbx
0x18000e9e5  push    rbp
0x18000e9e6  push    rsi
0x18000e9e7  push    rdi
0x18000e9e8  push    r12
0x18000e9ea  push    r13
0x18000e9ec  push    r14
0x18000e9ee  push    r15
0x18000e9f0  sub     rsp, 30h
0x18000e9f4  xor     r14d, r14d
0x18000e9f7  mov     rsi, r8
0x18000e9fa  mov     rdi, rdx
0x18000e9fd  mov     rbx, rcx
0x18000ea00  mov     [rsp+68h+arg_10], r14
0x18000ea08  cmp     [r8], r14
0x18000ea0b  jnz     short loc_18000EA3A
0x18000ea0d  mov     r8d, 0ABh; int
0x18000ea13  lea     r9, aErrorD_0; "Error = %d"
0x18000ea1a  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000ea22  lea     rdx, aWdipreadparame; "WdipReadParameterFromMessageBuffer"
0x18000ea29  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000ea30  call    WdipTraceError
0x18000ea35  jmp     loc_18000ED37
0x18000ea3a  test    rbx, rbx
0x18000ea3d  jnz     short loc_18000EA47
0x18000ea3f  mov     r8d, 0ACh
0x18000ea45  jmp     short loc_18000EA13
0x18000ea47  mov     ecx, 40h ; '@'
0x18000ea4c  call    WdipAlloc
0x18000ea51  mov     [rsp+68h+arg_18], rax
0x18000ea59  mov     rbp, rax
0x18000ea5c  test    rax, rax
0x18000ea5f  jnz     short loc_18000EA6F
0x18000ea61  mov     r8d, 0AFh
0x18000ea67  lea     eax, [rbp+0Eh]
0x18000ea6a  jmp     loc_18000ED07
0x18000ea6f  mov     rcx, [rsi]
0x18000ea72  mov     [rax+30h], r14
0x18000ea76  mov     [rax+38h], r14
0x18000ea7a  test    rcx, rcx
0x18000ea7d  jz      loc_18000ECFC
0x18000ea83  cmp     rcx, rbx
0x18000ea86  jb      loc_18000ECFC
0x18000ea8c  mov     rdx, rcx
0x18000ea8f  sub     rdx, rbx
0x18000ea92  cmp     rdx, rdi
0x18000ea95  ja      loc_18000ECFC
0x18000ea9b  mov     r9, rbx
0x18000ea9e  sub     r9, rcx
0x18000eaa1  add     r9, rdi
0x18000eaa4  cmp     r9, 10h
0x18000eaa8  jb      loc_18000ECFC
0x18000eaae  movups  xmm0, xmmword ptr [rcx]
0x18000eab1  lea     r8, [rcx+10h]
0x18000eab5  mov     [rsi], r8
0x18000eab8  movdqu  xmmword ptr [rax], xmm0
0x18000eabc  test    r8, r8
0x18000eabf  jz      short loc_18000EACF
0x18000eac1  cmp     r8, rbx
0x18000eac4  jb      short loc_18000EACF
0x18000eac6  lea     rax, [rdx+10h]
0x18000eaca  cmp     rax, rdi
0x18000eacd  jbe     short loc_18000EADA
0x18000eacf  mov     r8d, 0C3h
0x18000ead5  jmp     loc_18000ED02
0x18000eada  lea     rax, [r9-10h]
0x18000eade  cmp     rax, 10h
0x18000eae2  jb      short loc_18000EACF
0x18000eae4  movups  xmm0, xmmword ptr [r8]
0x18000eae8  lea     r8, [rcx+20h]
0x18000eaec  mov     [rsi], r8
0x18000eaef  movdqu  xmmword ptr [rbp+10h], xmm0
0x18000eaf4  test    r8, r8
0x18000eaf7  jz      short loc_18000EB07
0x18000eaf9  cmp     r8, rbx
0x18000eafc  jb      short loc_18000EB07
0x18000eafe  lea     rax, [rdx+20h]
0x18000eb02  cmp     rax, rdi
0x18000eb05  jbe     short loc_18000EB12
0x18000eb07  mov     r8d, 0CEh
0x18000eb0d  jmp     loc_18000ED02
0x18000eb12  lea     rax, [r9-20h]
0x18000eb16  cmp     rax, 4
0x18000eb1a  jb      short loc_18000EB07
0x18000eb1c  mov     eax, [r8]
0x18000eb1f  lea     r8, [rcx+24h]
0x18000eb23  mov     [rbp+20h], eax
0x18000eb26  mov     [rsi], r8
0x18000eb29  test    r8, r8
0x18000eb2c  jz      short loc_18000EB3C
0x18000eb2e  cmp     r8, rbx
0x18000eb31  jb      short loc_18000EB3C
0x18000eb33  lea     rax, [rdx+24h]
0x18000eb37  cmp     rax, rdi
0x18000eb3a  jbe     short loc_18000EB47
0x18000eb3c  mov     r8d, 0D9h
0x18000eb42  jmp     loc_18000ED02
0x18000eb47  lea     rax, [r9-24h]
0x18000eb4b  cmp     rax, 4
0x18000eb4f  jb      short loc_18000EB3C
0x18000eb51  mov     eax, [r8]
0x18000eb54  lea     r8, [rcx+28h]
0x18000eb58  mov     [rbp+24h], eax
0x18000eb5b  mov     [rsi], r8
0x18000eb5e  test    r8, r8
0x18000eb61  jz      short loc_18000EB71
0x18000eb63  cmp     r8, rbx
0x18000eb66  jb      short loc_18000EB71
0x18000eb68  lea     rax, [rdx+28h]
0x18000eb6c  cmp     rax, rdi
0x18000eb6f  jbe     short loc_18000EB7C
0x18000eb71  mov     r8d, 0E4h
0x18000eb77  jmp     loc_18000ED02
0x18000eb7c  lea     rax, [r9-28h]
0x18000eb80  cmp     rax, 4
0x18000eb84  jb      short loc_18000EB71
0x18000eb86  mov     eax, [r8]
0x18000eb89  add     rcx, 2Ch ; ','
0x18000eb8d  mov     [rsi], rcx
0x18000eb90  mov     [rbp+2Ch], eax
0x18000eb93  jz      short loc_18000EBA5
0x18000eb95  cmp     rcx, rbx
0x18000eb98  jb      short loc_18000EBA5
0x18000eb9a  mov     rax, rcx
0x18000eb9d  sub     rax, rbx
0x18000eba0  cmp     rax, rdi
0x18000eba3  jbe     short loc_18000EBB0
0x18000eba5  mov     r8d, 0EFh
0x18000ebab  jmp     loc_18000ED02
0x18000ebb0  mov     rax, rbx
0x18000ebb3  sub     rax, rcx
0x18000ebb6  add     rax, rdi
0x18000ebb9  cmp     rax, 4
0x18000ebbd  jb      short loc_18000EBA5
0x18000ebbf  mov     r14d, [rcx]
0x18000ebc2  lea     rax, [rcx+4]
0x18000ebc6  mov     [rsi], rax
0x18000ebc9  lea     eax, [r14+2]
0x18000ebcd  cmp     eax, r14d
0x18000ebd0  jnb     short loc_18000EBEA
0x18000ebd2  mov     r8d, 0FFh
0x18000ebd8  mov     eax, 216h
0x18000ebdd  mov     r14, [rsp+68h+arg_10]
0x18000ebe5  jmp     loc_18000ED07
0x18000ebea  mov     ecx, eax
0x18000ebec  mov     r15d, eax
0x18000ebef  call    WdipAlloc
0x18000ebf4  mov     [rbp+30h], rax
0x18000ebf8  test    rax, rax
0x18000ebfb  jnz     short loc_18000EC0A
0x18000ebfd  mov     r8d, 102h
0x18000ec03  mov     eax, 0Eh
0x18000ec08  jmp     short loc_18000EBDD
0x18000ec0a  mov     r8, r15; Size
0x18000ec0d  xor     edx, edx; Val
0x18000ec0f  mov     rcx, rax; void *
0x18000ec12  call    memset_0
0x18000ec17  mov     r15, [rsi]
0x18000ec1a  test    r15, r15
0x18000ec1d  jz      short loc_18000EC2F
0x18000ec1f  cmp     r15, rbx
0x18000ec22  jb      short loc_18000EC2F
0x18000ec24  mov     r12, r15
0x18000ec27  sub     r12, rbx
0x18000ec2a  cmp     r12, rdi
0x18000ec2d  jbe     short loc_18000EC42
0x18000ec2f  mov     r8d, 109h
0x18000ec35  mov     r14, [rsp+68h+arg_10]
0x18000ec3d  jmp     loc_18000ED02
0x18000ec42  mov     r13, r14
0x18000ec45  mov     r14, rbx
0x18000ec48  sub     r14, r15
0x18000ec4b  lea     rax, [r14+rdi]
0x18000ec4f  cmp     r13, rax
0x18000ec52  ja      short loc_18000EC2F
0x18000ec54  mov     rcx, [rbp+30h]; void *
0x18000ec58  mov     r8, r13; Size
0x18000ec5b  mov     rdx, r15; Src
0x18000ec5e  call    memcpy_0
0x18000ec63  lea     rdx, [r15+r13]
0x18000ec67  mov     [rsi], rdx
0x18000ec6a  test    rdx, rdx
0x18000ec6d  jz      short loc_18000EC7D
0x18000ec6f  cmp     rdx, rbx
0x18000ec72  jb      short loc_18000EC7D
0x18000ec74  lea     rax, [r12+r13]
0x18000ec78  cmp     rax, rdi
0x18000ec7b  jbe     short loc_18000EC85
0x18000ec7d  mov     r8d, 114h
0x18000ec83  jmp     short loc_18000EC35
0x18000ec85  sub     r14, r13
0x18000ec88  add     r14, rdi
0x18000ec8b  cmp     r14, 4
0x18000ec8f  jb      short loc_18000EC7D
0x18000ec91  mov     ecx, [rdx]
0x18000ec93  lea     rax, [rdx+4]
0x18000ec97  mov     [rbp+28h], ecx
0x18000ec9a  mov     [rsi], rax
0x18000ec9d  call    WdipAlloc
0x18000eca2  mov     [rbp+38h], rax
0x18000eca6  mov     rcx, rax; void *
0x18000eca9  test    rax, rax
0x18000ecac  jnz     short loc_18000ECB9
0x18000ecae  mov     r8d, 11Ch
0x18000ecb4  jmp     loc_18000EC03
0x18000ecb9  cmp     qword ptr [rsi], 0
0x18000ecbd  jz      short loc_18000ECCF
0x18000ecbf  cmp     [rsi], rbx
0x18000ecc2  jb      short loc_18000ECCF
0x18000ecc4  mov     rax, [rsi]
0x18000ecc7  sub     rax, rbx
0x18000ecca  cmp     rax, rdi
0x18000eccd  jbe     short loc_18000ECDA
0x18000eccf  mov     r8d, 122h
0x18000ecd5  jmp     loc_18000EC35
0x18000ecda  sub     rbx, [rsi]
0x18000ecdd  mov     r8d, [rbp+28h]; Size
0x18000ece1  add     rbx, rdi
0x18000ece4  cmp     r8, rbx
0x18000ece7  ja      short loc_18000ECCF
0x18000ece9  mov     rdx, [rsi]; Src
0x18000ecec  call    memcpy_0
0x18000ecf1  mov     eax, [rbp+28h]
0x18000ecf4  mov     r14, rbp
0x18000ecf7  add     [rsi], rax
0x18000ecfa  jmp     short loc_18000ED37
0x18000ecfc  mov     r8d, 0B8h; int
0x18000ed02  mov     eax, 6Fh ; 'o'
0x18000ed07  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000ed0e  lea     rdx, aWdipreadparame; "WdipReadParameterFromMessageBuffer"
0x18000ed15  lea     r9, aErrorD_0; "Error = %d"
0x18000ed1c  mov     dword ptr [rsp+68h+Args], eax; Args
0x18000ed20  call    WdipTraceError
0x18000ed25  test    rbp, rbp
0x18000ed28  jz      short loc_18000ED37
0x18000ed2a  lea     rcx, [rsp+68h+arg_18]
0x18000ed32  call    WdipDeleteParameter
0x18000ed37  mov     rbx, [rsp+68h+arg_0]
0x18000ed3c  mov     rax, r14
0x18000ed3f  add     rsp, 30h
0x18000ed43  pop     r15
0x18000ed45  pop     r14
0x18000ed47  pop     r13
0x18000ed49  pop     r12
0x18000ed4b  pop     rdi
0x18000ed4c  pop     rsi
0x18000ed4d  pop     rbp
0x18000ed4e  retn
```
