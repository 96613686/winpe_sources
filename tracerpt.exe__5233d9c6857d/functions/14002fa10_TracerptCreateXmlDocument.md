# TracerptCreateXmlDocument

- ea: `0x14002fa10`
- end: `0x14002fb9e`
- name: `TracerptCreateXmlDocument`
- size: `398`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002f7ec`
- `0x14002fba4`

## callees

- `0x14002fa10`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002fa6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002fa6d`
- `OLEAUT32!__imp_SysAllocString` at `0x14002fadb`
- `OLEAUT32!__imp_SysAllocString` at `0x14002fadb`
- `OLEAUT32!__imp_VariantInit` at `0x14002fa4a`
- `OLEAUT32!__imp_VariantInit` at `0x14002fa4a`
- `OLEAUT32!__imp_VariantClear` at `0x14002fb71`
- `OLEAUT32!__imp_VariantClear` at `0x14002fb71`

## pseudocode

```c
__int64 __fastcall TracerptCreateXmlDocument(__int64 a1, __int128 *a2, const OLECHAR *a3, __int64 a4)
{
  HRESULT v8; // ebx
  int v9; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  __int128 v11; // xmm0
  __int16 v13; // [rsp+30h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-19h] BYREF
  __int128 v16; // [rsp+60h] [rbp+7h] BYREF
  IRecordInfo *v17; // [rsp+70h] [rbp+17h]

  v13 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  ppv = 0;
  VariantInit(&pvarg);
  v8 = CoCreateInstance(
         &GUID_88d96a06_f192_11d4_a65f_0040963251e5,
         0,
         0x15u,
         &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 576LL))(ppv, 0);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
      if ( v8 >= 0 )
      {
        if ( a4 )
        {
          v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, a4, &v13);
        }
        else
        {
          if ( a3 )
          {
            pvarg.llVal = (LONGLONG)SysAllocString(a3);
            if ( !pvarg.llVal )
            {
              v8 = -2147024882;
              goto LABEL_18;
            }
            pRecInfo = pvarg.pRecInfo;
            pvarg.vt = 8;
            v11 = *(_OWORD *)&pvarg.vt;
          }
          else
          {
            if ( !a2 )
            {
              v8 = -2147024809;
              goto LABEL_18;
            }
            v11 = *a2;
            pRecInfo = (IRecordInfo *)*((_QWORD *)a2 + 2);
          }
          v17 = pRecInfo;
          v16 = v11;
          v9 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int16 *))(*(_QWORD *)ppv + 464LL))(ppv, &v16, &v13);
        }
        v8 = v9;
        if ( v9 >= 0 )
        {
          if ( v13 )
            v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(
                   ppv,
                   &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
                   a1);
          else
            v8 = -2147467259;
        }
      }
    }
  }
LABEL_18:
  VariantClear(&pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002fa10  push    rbp
0x14002fa12  push    rbx
0x14002fa13  push    rsi
0x14002fa14  push    rdi
0x14002fa15  push    r14
0x14002fa17  push    r15
0x14002fa19  lea     rbp, [rsp-2Fh]
0x14002fa1e  sub     rsp, 88h
0x14002fa25  xor     eax, eax
0x14002fa27  mov     r15, rcx
0x14002fa2a  xorps   xmm0, xmm0
0x14002fa2d  mov     [rbp+57h+var_80], ax
0x14002fa31  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14002fa35  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x14002fa39  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14002fa3d  mov     [rbp+57h+var_78], rax
0x14002fa41  mov     r14, r9
0x14002fa44  mov     rdi, r8
0x14002fa47  mov     rsi, rdx
0x14002fa4a  call    cs:__imp_VariantInit
0x14002fa50  xor     edx, edx; pUnkOuter
0x14002fa52  lea     rax, [rbp+57h+var_78]
0x14002fa56  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x14002fa5d  mov     [rsp+0B0h+ppv], rax; ppv
0x14002fa62  lea     rcx, _GUID_88d96a06_f192_11d4_a65f_0040963251e5; rclsid
0x14002fa69  lea     r8d, [rdx+15h]; dwClsContext
0x14002fa6d  call    cs:__imp_CoCreateInstance
0x14002fa73  mov     ebx, eax
0x14002fa75  test    eax, eax
0x14002fa77  js      loc_14002FB6D
0x14002fa7d  mov     rcx, [rbp+57h+var_78]
0x14002fa81  xor     edx, edx
0x14002fa83  mov     rax, [rcx]
0x14002fa86  mov     rax, [rax+240h]
0x14002fa8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fa92  mov     ebx, eax
0x14002fa94  test    eax, eax
0x14002fa96  js      loc_14002FB6D
0x14002fa9c  mov     rcx, [rbp+57h+var_78]
0x14002faa0  xor     edx, edx
0x14002faa2  mov     rax, [rcx]
0x14002faa5  mov     rax, [rax+1F8h]
0x14002faac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fab1  mov     ebx, eax
0x14002fab3  test    eax, eax
0x14002fab5  js      loc_14002FB6D
0x14002fabb  test    r14, r14
0x14002fabe  jz      short loc_14002FAD3
0x14002fac0  mov     rcx, [rbp+57h+var_78]
0x14002fac4  mov     rdx, r14
0x14002fac7  mov     rax, [rcx]
0x14002faca  mov     rax, [rax+208h]
0x14002fad1  jmp     short loc_14002FB2D
0x14002fad3  test    rdi, rdi
0x14002fad6  jz      short loc_14002FB05
0x14002fad8  mov     rcx, rdi; psz
0x14002fadb  call    cs:__imp_SysAllocString
0x14002fae1  mov     qword ptr [rbp+57h+pvarg+8], rax
0x14002fae5  test    rax, rax
0x14002fae8  jnz     short loc_14002FAF1
0x14002faea  mov     ebx, 8007000Eh
0x14002faef  jmp     short loc_14002FB6D
0x14002faf1  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x14002faf6  mov     eax, 8
0x14002fafb  mov     word ptr [rbp+57h+pvarg], ax
0x14002faff  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x14002fb03  jmp     short loc_14002FB12
0x14002fb05  test    rsi, rsi
0x14002fb08  jz      short loc_14002FB68
0x14002fb0a  movups  xmm0, xmmword ptr [rsi]
0x14002fb0d  movsd   xmm1, qword ptr [rsi+10h]
0x14002fb12  mov     rcx, [rbp+57h+var_78]
0x14002fb16  lea     rdx, [rbp+57h+var_50]
0x14002fb1a  movsd   [rbp+57h+var_40], xmm1
0x14002fb1f  movaps  [rbp+57h+var_50], xmm0
0x14002fb23  mov     rax, [rcx]
0x14002fb26  mov     rax, [rax+1D0h]
0x14002fb2d  lea     r8, [rbp+57h+var_80]
0x14002fb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fb36  mov     ebx, eax
0x14002fb38  test    eax, eax
0x14002fb3a  js      short loc_14002FB6D
0x14002fb3c  xor     eax, eax
0x14002fb3e  cmp     ax, [rbp+57h+var_80]
0x14002fb42  jnz     short loc_14002FB4B
0x14002fb44  mov     ebx, 80004005h
0x14002fb49  jmp     short loc_14002FB6D
0x14002fb4b  mov     rcx, [rbp+57h+var_78]
0x14002fb4f  lea     rdx, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60
0x14002fb56  mov     r8, r15
0x14002fb59  mov     rax, [rcx]
0x14002fb5c  mov     rax, [rax]
0x14002fb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fb64  mov     ebx, eax
0x14002fb66  jmp     short loc_14002FB6D
0x14002fb68  mov     ebx, 80070057h
0x14002fb6d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14002fb71  call    cs:__imp_VariantClear
0x14002fb77  mov     rcx, [rbp+57h+var_78]
0x14002fb7b  test    rcx, rcx
0x14002fb7e  jz      short loc_14002FB8C
0x14002fb80  mov     rax, [rcx]
0x14002fb83  mov     rax, [rax+10h]
0x14002fb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fb8c  mov     eax, ebx
0x14002fb8e  add     rsp, 88h
0x14002fb95  pop     r15
0x14002fb97  pop     r14
0x14002fb99  pop     rdi
0x14002fb9a  pop     rsi
0x14002fb9b  pop     rbx
0x14002fb9c  pop     rbp
0x14002fb9d  retn
```
