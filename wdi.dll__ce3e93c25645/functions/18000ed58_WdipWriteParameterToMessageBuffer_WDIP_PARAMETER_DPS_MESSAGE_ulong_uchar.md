# WdipWriteParameterToMessageBuffer(__WDIP_PARAMETER *,_DPS_MESSAGE *,ulong,uchar * *)

- ea: `0x18000ed58`
- end: `0x18000f086`
- name: `?WdipWriteParameterToMessageBuffer@@YAJPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@KPEAPEAE@Z`
- size: `814`
- prototype: `__int64 __fastcall(struct __WDIP_PARAMETER *, struct _DPS_MESSAGE *, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007d40`

## callees

- `0x180002ba0`
- `0x180009444`
- `0x180009540`
- `0x18000ed58`
- `0x18000f1b6`

## string_xrefs

- `0x18000edb0`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000f05a`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000eda9`: `WdipWriteParameterToMessageBuffer`
- `0x18000f053`: `WdipWriteParameterToMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipWriteParameterToMessageBuffer(
        struct __WDIP_PARAMETER *a1,
        struct _DPS_MESSAGE *a2,
        unsigned int a3,
        unsigned __int8 **a4)
{
  unsigned __int64 v4; // rsi
  int v8; // r8d
  unsigned int v9; // ebx
  HRESULT Args; // eax
  int v11; // eax
  unsigned __int64 v12; // r11
  unsigned __int64 v13; // rcx
  char *v14; // r8
  __int128 v15; // xmm0
  struct _DPS_MESSAGE *v16; // rdx
  int v17; // r8d
  struct _DPS_MESSAGE *v18; // rdx
  struct _DPS_MESSAGE *v19; // rdx
  struct _DPS_MESSAGE *v20; // rdx
  int v21; // eax
  bool v22; // zf
  unsigned __int8 *v23; // r11
  unsigned int v24; // eax
  unsigned __int64 v25; // rbp
  unsigned int v26; // ecx
  __int64 v27; // r12
  unsigned __int8 *v28; // rbp
  unsigned __int8 *v29; // rbp
  size_t v30; // r8
  unsigned __int64 v32; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v33; // [rsp+70h] [rbp+8h] BYREF

  v4 = a3;
  v33 = 0;
  v32 = 0;
  if ( !a1 )
  {
    v8 = 471;
LABEL_3:
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipWriteParameterToMessageBuffer",
      v8,
      (int)L"Error = %d",
      87);
    return v9;
  }
  if ( !a2 )
  {
    v8 = 472;
    goto LABEL_3;
  }
  if ( !*a4 )
  {
    v8 = 473;
    goto LABEL_3;
  }
  Args = StringCchLengthW(*((const unsigned __int16 **)a1 + 6), 0x7FFFFFFFu, &v32);
  v9 = Args;
  if ( Args >= 0 )
  {
    v11 = ULongLongToULong(v32, &v33);
    v9 = v11;
    if ( v11 >= 0 )
    {
      if ( v12 < (unsigned __int64)a2
        || (v13 = v12 - (_QWORD)a2, v12 - (unsigned __int64)a2 > v4)
        || (v14 = (char *)a2 + v4 - v12, (unsigned __int64)v14 < 0x10) )
      {
        v17 = 490;
      }
      else
      {
        v15 = *(_OWORD *)a1;
        v16 = (struct _DPS_MESSAGE *)(v12 + 16);
        *a4 = (unsigned __int8 *)(v12 + 16);
        *(_OWORD *)v12 = v15;
        if ( v12 == -16 || v16 < a2 || v13 + 16 > v4 || (unsigned __int64)(v14 - 16) < 0x10 )
        {
          v17 = 501;
        }
        else
        {
          *(_OWORD *)v16 = *((_OWORD *)a1 + 1);
          v18 = (struct _DPS_MESSAGE *)(v12 + 32);
          *a4 = (unsigned __int8 *)(v12 + 32);
          if ( v12 == -32 || v18 < a2 || v13 + 32 > v4 || (unsigned __int64)(v14 - 32) < 4 )
          {
            v17 = 512;
          }
          else
          {
            *(_DWORD *)v18 = *((_DWORD *)a1 + 8);
            v19 = (struct _DPS_MESSAGE *)(v12 + 36);
            *a4 = (unsigned __int8 *)(v12 + 36);
            if ( v12 == -36 || v19 < a2 || v13 + 36 > v4 || (unsigned __int64)(v14 - 36) < 4 )
            {
              v17 = 523;
            }
            else
            {
              *(_DWORD *)v19 = *((_DWORD *)a1 + 9);
              v20 = (struct _DPS_MESSAGE *)(v12 + 40);
              *a4 = (unsigned __int8 *)(v12 + 40);
              if ( v12 == -40 || v20 < a2 || v13 + 40 > v4 || (unsigned __int64)(v14 - 40) < 4 )
              {
                v17 = 534;
              }
              else
              {
                v21 = *((_DWORD *)a1 + 11);
                v22 = v12 == -44;
                v23 = (unsigned __int8 *)(v12 + 44);
                *a4 = v23;
                *(_DWORD *)v20 = v21;
                if ( v22
                  || v23 < (unsigned __int8 *)a2
                  || v23 - (unsigned __int8 *)a2 > v4
                  || (unsigned __int64)a2 + v4 - (_QWORD)v23 < 4 )
                {
                  v17 = 545;
                }
                else
                {
                  v24 = v33;
                  v25 = (unsigned __int64)(v23 + 4);
                  *a4 = v23 + 4;
                  v26 = 2 * v24 + 2;
                  *(_DWORD *)v23 = v26;
                  if ( v23 == (unsigned __int8 *)-4LL
                    || v25 < (unsigned __int64)a2
                    || v25 - (unsigned __int64)a2 > v4
                    || (v27 = v26, v26 > (unsigned __int64)a2 + v4 - v25) )
                  {
                    v17 = 556;
                  }
                  else
                  {
                    memcpy_0(v23 + 4, *((const void **)a1 + 6), v26);
                    v22 = v27 + v25 == 0;
                    v28 = (unsigned __int8 *)(v27 + v25);
                    *a4 = v28;
                    if ( v22
                      || v28 < (unsigned __int8 *)a2
                      || v28 - (unsigned __int8 *)a2 > v4
                      || (unsigned __int64)a2 + v4 - (_QWORD)v28 < 4 )
                    {
                      v17 = 567;
                    }
                    else
                    {
                      *(_DWORD *)v28 = *((_DWORD *)a1 + 10);
                      v22 = v28 + 4 == 0;
                      v29 = v28 + 4;
                      *a4 = v29;
                      if ( !v22 && v29 >= (unsigned __int8 *)a2 && v29 - (unsigned __int8 *)a2 <= v4 )
                      {
                        v30 = *((unsigned int *)a1 + 10);
                        if ( v30 <= (unsigned __int64)a2 + v4 - (_QWORD)v29 )
                        {
                          memcpy_0(v29, *((const void **)a1 + 7), v30);
                          *a4 = &v29[*((unsigned int *)a1 + 10)];
                          return v9;
                        }
                      }
                      v17 = 578;
                    }
                  }
                }
              }
            }
          }
        }
      }
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
        (int)L"WdipWriteParameterToMessageBuffer",
        v17,
        (int)L"Error = %d",
        111);
      return (unsigned int)-2147024362;
    }
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipWriteParameterToMessageBuffer",
      482,
      (int)L"Error = %d",
      v11);
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipWriteParameterToMessageBuffer",
      479,
      (int)L"Error = %d",
      Args);
  }
  return v9;
}

```

## disassembly

```asm
0x18000ed58  mov     rax, rsp
0x18000ed5b  mov     [rax+10h], rbx
0x18000ed5f  mov     [rax+18h], rbp
0x18000ed63  push    rsi
0x18000ed64  push    rdi
0x18000ed65  push    r12
0x18000ed67  push    r14
0x18000ed69  push    r15
0x18000ed6b  sub     rsp, 40h
0x18000ed6f  mov     esi, r8d
0x18000ed72  mov     r15, r9
0x18000ed75  mov     dword ptr [rax+8], 0
0x18000ed7c  mov     rdi, rdx
0x18000ed7f  mov     qword ptr [rax-38h], 0
0x18000ed87  mov     r14, rcx
0x18000ed8a  test    rcx, rcx
0x18000ed8d  jnz     short loc_18000EDC1
0x18000ed8f  mov     r8d, 1D7h; int
0x18000ed95  mov     ebx, 80070057h
0x18000ed9a  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000eda2  lea     r9, aErrorD_0; "Error = %d"
0x18000eda9  lea     rdx, aWdipwriteparam; "WdipWriteParameterToMessageBuffer"
0x18000edb0  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000edb7  call    WdipTraceError
0x18000edbc  jmp     loc_18000F06B
0x18000edc1  test    rdi, rdi
0x18000edc4  jnz     short loc_18000EDCE
0x18000edc6  mov     r8d, 1D8h
0x18000edcc  jmp     short loc_18000ED95
0x18000edce  mov     r11, [r9]
0x18000edd1  test    r11, r11
0x18000edd4  jnz     short loc_18000EDDE
0x18000edd6  mov     r8d, 1D9h
0x18000eddc  jmp     short loc_18000ED95
0x18000edde  mov     rcx, [rcx+30h]; unsigned __int16 *
0x18000ede2  lea     r8, [rsp+68h+var_38]; unsigned __int64 *
0x18000ede7  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000edec  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000edf1  mov     ebx, eax
0x18000edf3  test    eax, eax
0x18000edf5  jns     short loc_18000EE06
0x18000edf7  movzx   ecx, ax
0x18000edfa  mov     r8d, 1DFh
0x18000ee00  mov     dword ptr [rsp+68h+Args], ecx
0x18000ee04  jmp     short loc_18000EDA2
0x18000ee06  mov     rcx, [rsp+68h+var_38]; unsigned __int64
0x18000ee0b  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x18000ee10  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000ee15  mov     ebx, eax
0x18000ee17  test    eax, eax
0x18000ee19  jns     short loc_18000EE2D
0x18000ee1b  movzx   eax, ax
0x18000ee1e  mov     r8d, 1E2h
0x18000ee24  mov     dword ptr [rsp+68h+Args], eax
0x18000ee28  jmp     loc_18000EDA2
0x18000ee2d  cmp     r11, rdi
0x18000ee30  jb      loc_18000F03E
0x18000ee36  mov     rcx, r11
0x18000ee39  sub     rcx, rdi
0x18000ee3c  cmp     rcx, rsi
0x18000ee3f  ja      loc_18000F03E
0x18000ee45  mov     r8, rsi
0x18000ee48  sub     r8, r11
0x18000ee4b  add     r8, rdi
0x18000ee4e  cmp     r8, 10h
0x18000ee52  jb      loc_18000F03E
0x18000ee58  movups  xmm0, xmmword ptr [r14]
0x18000ee5c  lea     rdx, [r11+10h]
0x18000ee60  mov     [r15], rdx
0x18000ee63  movdqu  xmmword ptr [r11], xmm0
0x18000ee68  test    rdx, rdx
0x18000ee6b  jz      short loc_18000EE7B
0x18000ee6d  cmp     rdx, rdi
0x18000ee70  jb      short loc_18000EE7B
0x18000ee72  lea     rax, [rcx+10h]
0x18000ee76  cmp     rax, rsi
0x18000ee79  jbe     short loc_18000EE86
0x18000ee7b  mov     r8d, 1F5h
0x18000ee81  jmp     loc_18000F044
0x18000ee86  lea     rax, [r8-10h]
0x18000ee8a  cmp     rax, 10h
0x18000ee8e  jb      short loc_18000EE7B
0x18000ee90  movups  xmm0, xmmword ptr [r14+10h]
0x18000ee95  movdqu  xmmword ptr [rdx], xmm0
0x18000ee99  lea     rdx, [r11+20h]
0x18000ee9d  mov     [r15], rdx
0x18000eea0  test    rdx, rdx
0x18000eea3  jz      short loc_18000EEB3
0x18000eea5  cmp     rdx, rdi
0x18000eea8  jb      short loc_18000EEB3
0x18000eeaa  lea     rax, [rcx+20h]
0x18000eeae  cmp     rax, rsi
0x18000eeb1  jbe     short loc_18000EEBE
0x18000eeb3  mov     r8d, 200h
0x18000eeb9  jmp     loc_18000F044
0x18000eebe  lea     rax, [r8-20h]
0x18000eec2  cmp     rax, 4
0x18000eec6  jb      short loc_18000EEB3
0x18000eec8  mov     eax, [r14+20h]
0x18000eecc  mov     [rdx], eax
0x18000eece  lea     rdx, [r11+24h]
0x18000eed2  mov     [r15], rdx
0x18000eed5  test    rdx, rdx
0x18000eed8  jz      short loc_18000EEE8
0x18000eeda  cmp     rdx, rdi
0x18000eedd  jb      short loc_18000EEE8
0x18000eedf  lea     rax, [rcx+24h]
0x18000eee3  cmp     rax, rsi
0x18000eee6  jbe     short loc_18000EEF3
0x18000eee8  mov     r8d, 20Bh
0x18000eeee  jmp     loc_18000F044
0x18000eef3  lea     rax, [r8-24h]
0x18000eef7  cmp     rax, 4
0x18000eefb  jb      short loc_18000EEE8
0x18000eefd  mov     eax, [r14+24h]
0x18000ef01  mov     [rdx], eax
0x18000ef03  lea     rdx, [r11+28h]
0x18000ef07  mov     [r15], rdx
0x18000ef0a  test    rdx, rdx
0x18000ef0d  jz      short loc_18000EF1D
0x18000ef0f  cmp     rdx, rdi
0x18000ef12  jb      short loc_18000EF1D
0x18000ef14  lea     rax, [rcx+28h]
0x18000ef18  cmp     rax, rsi
0x18000ef1b  jbe     short loc_18000EF28
0x18000ef1d  mov     r8d, 216h
0x18000ef23  jmp     loc_18000F044
0x18000ef28  lea     rax, [r8-28h]
0x18000ef2c  cmp     rax, 4
0x18000ef30  jb      short loc_18000EF1D
0x18000ef32  mov     eax, [r14+2Ch]
0x18000ef36  add     r11, 2Ch ; ','
0x18000ef3a  mov     [r15], r11
0x18000ef3d  mov     [rdx], eax
0x18000ef3f  jz      short loc_18000EF51
0x18000ef41  cmp     r11, rdi
0x18000ef44  jb      short loc_18000EF51
0x18000ef46  mov     rax, r11
0x18000ef49  sub     rax, rdi
0x18000ef4c  cmp     rax, rsi
0x18000ef4f  jbe     short loc_18000EF5C
0x18000ef51  mov     r8d, 221h
0x18000ef57  jmp     loc_18000F044
0x18000ef5c  mov     rax, rsi
0x18000ef5f  sub     rax, r11
0x18000ef62  add     rax, rdi
0x18000ef65  cmp     rax, 4
0x18000ef69  jb      short loc_18000EF51
0x18000ef6b  mov     eax, [rsp+68h+arg_0]
0x18000ef6f  lea     rbp, [r11+4]
0x18000ef73  mov     [r15], rbp
0x18000ef76  lea     ecx, ds:2[rax*2]
0x18000ef7d  mov     [r11], ecx
0x18000ef80  test    rbp, rbp
0x18000ef83  jz      short loc_18000EF95
0x18000ef85  cmp     rbp, rdi
0x18000ef88  jb      short loc_18000EF95
0x18000ef8a  mov     rax, rbp
0x18000ef8d  sub     rax, rdi
0x18000ef90  cmp     rax, rsi
0x18000ef93  jbe     short loc_18000EFA0
0x18000ef95  mov     r8d, 22Ch
0x18000ef9b  jmp     loc_18000F044
0x18000efa0  mov     rax, rsi
0x18000efa3  mov     r12d, ecx
0x18000efa6  sub     rax, rbp
0x18000efa9  add     rax, rdi
0x18000efac  cmp     r12, rax
0x18000efaf  ja      short loc_18000EF95
0x18000efb1  mov     rdx, [r14+30h]; Src
0x18000efb5  mov     r8d, r12d; Size
0x18000efb8  mov     rcx, rbp; void *
0x18000efbb  call    memcpy_0
0x18000efc0  add     rbp, r12
0x18000efc3  mov     [r15], rbp
0x18000efc6  jz      short loc_18000EFD8
0x18000efc8  cmp     rbp, rdi
0x18000efcb  jb      short loc_18000EFD8
0x18000efcd  mov     rax, rbp
0x18000efd0  sub     rax, rdi
0x18000efd3  cmp     rax, rsi
0x18000efd6  jbe     short loc_18000EFE0
0x18000efd8  mov     r8d, 237h
0x18000efde  jmp     short loc_18000F044
0x18000efe0  mov     rax, rsi
0x18000efe3  sub     rax, rbp
0x18000efe6  add     rax, rdi
0x18000efe9  cmp     rax, 4
0x18000efed  jb      short loc_18000EFD8
0x18000efef  mov     eax, [r14+28h]
0x18000eff3  mov     [rbp+0], eax
0x18000eff6  add     rbp, 4
0x18000effa  mov     [r15], rbp
0x18000effd  jz      short loc_18000F00F
0x18000efff  cmp     rbp, rdi
0x18000f002  jb      short loc_18000F00F
0x18000f004  mov     rax, rbp
0x18000f007  sub     rax, rdi
0x18000f00a  cmp     rax, rsi
0x18000f00d  jbe     short loc_18000F017
0x18000f00f  mov     r8d, 242h
0x18000f015  jmp     short loc_18000F044
0x18000f017  mov     r8d, [r14+28h]; Size
0x18000f01b  sub     rsi, rbp
0x18000f01e  add     rsi, rdi
0x18000f021  cmp     r8, rsi
0x18000f024  ja      short loc_18000F00F
0x18000f026  mov     rdx, [r14+38h]; Src
0x18000f02a  mov     rcx, rbp; void *
0x18000f02d  call    memcpy_0
0x18000f032  mov     eax, [r14+28h]
0x18000f036  add     rax, rbp
0x18000f039  mov     [r15], rax
0x18000f03c  jmp     short loc_18000F06B
0x18000f03e  mov     r8d, 1EAh; int
0x18000f044  lea     r9, aErrorD_0; "Error = %d"
0x18000f04b  mov     dword ptr [rsp+68h+Args], 6Fh ; 'o'; Args
0x18000f053  lea     rdx, aWdipwriteparam; "WdipWriteParameterToMessageBuffer"
0x18000f05a  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000f061  call    WdipTraceError
0x18000f066  mov     ebx, 80070216h
0x18000f06b  lea     r11, [rsp+68h+var_28]
0x18000f070  mov     eax, ebx
0x18000f072  mov     rbx, [r11+38h]
0x18000f076  mov     rbp, [r11+40h]
0x18000f07a  mov     rsp, r11
0x18000f07d  pop     r15
0x18000f07f  pop     r14
0x18000f081  pop     r12
0x18000f083  pop     rdi
0x18000f084  pop     rsi
0x18000f085  retn
```
