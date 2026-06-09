# AspCompatResponse::BinaryWrite(tagVARIANT)

- ea: `0x180005130`
- end: `0x18000524c`
- name: `?BinaryWrite@AspCompatResponse@@UEAAJUtagVARIANT@@@Z`
- size: `284`
- prototype: `int(AspCompatResponse *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005130`
- `0x180007b0c`
- `0x180065b60`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000514f`
- `OLEAUT32!__imp_VariantInit` at `0x18000514f`
- `OLEAUT32!__imp_VariantClear` at `0x180005239`
- `OLEAUT32!__imp_VariantClear` at `0x180005239`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000519a`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000519a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800051ad`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800051ad`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800051e1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800051e1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800051cb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800051cb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800051ff`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800051ff`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000522f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000522f`

## pseudocode

```c
__int64 __fastcall AspCompatResponse::BinaryWrite(AspCompatResponse *this, struct tagVARIANT *a2)
{
  SAFEARRAY *parray; // rdi
  __int64 v5; // r14
  unsigned int LBound; // ebx
  unsigned int v7; // esi
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  LONG plUbound; // [rsp+70h] [rbp+30h] BYREF
  LONG plLbound; // [rsp+80h] [rbp+40h] BYREF
  void *ppvData; // [rsp+88h] [rbp+48h] BYREF

  ppvData = 0;
  parray = 0;
  VariantInit(&pvarg);
  v5 = *(_QWORD *)(*((_QWORD *)this + 9) + 48LL);
  if ( v5 )
  {
    LBound = VariantDereferenceDefaultDispatchProperty(&pvarg, a2);
    if ( !LBound && (pvarg.vt == 8209 || (LBound = VariantChangeType(&pvarg, &pvarg, 0, 0x2011u)) == 0) )
    {
      parray = pvarg.parray;
      if ( SafeArrayGetDim(pvarg.parray) == 1 )
      {
        LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
        if ( !LBound )
        {
          LBound = SafeArrayGetUBound(parray, 1u, &plUbound);
          if ( !LBound )
          {
            v7 = plUbound - plLbound + 1;
            if ( plUbound - plLbound != -1 )
            {
              LBound = SafeArrayAccessData(parray, &ppvData);
              if ( !LBound )
                (*(void (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v5 + 208LL))(v5, ppvData, v7);
            }
          }
        }
      }
      else
      {
        LBound = -2147024809;
      }
    }
  }
  else
  {
    LBound = -2147418113;
  }
  if ( ppvData )
    SafeArrayUnaccessData(parray);
  VariantClear(&pvarg);
  return LBound;
}

```

## disassembly

```asm
0x180005130  push    rbp
0x180005132  push    rbx
0x180005133  push    rsi
0x180005134  push    rdi
0x180005135  push    r14
0x180005137  mov     rbp, rsp
0x18000513a  sub     rsp, 40h
0x18000513e  and     [rbp+ppvData], 0
0x180005143  mov     rbx, rcx
0x180005146  lea     rcx, [rbp+pvarg]; pvarg
0x18000514a  mov     rsi, rdx
0x18000514d  xor     edi, edi
0x18000514f  call    cs:__imp_VariantInit
0x180005155  mov     rax, [rbx+48h]
0x180005159  mov     r14, [rax+30h]
0x18000515d  test    r14, r14
0x180005160  jnz     short loc_18000516C
0x180005162  mov     ebx, 8000FFFFh
0x180005167  jmp     loc_180005225
0x18000516c  mov     rdx, rsi; pvargSrc
0x18000516f  lea     rcx, [rbp+pvarg]; pvarg
0x180005173  call    ?VariantDereferenceDefaultDispatchProperty@@YAJPEAUtagVARIANT@@0@Z; VariantDereferenceDefaultDispatchProperty(tagVARIANT *,tagVARIANT *)
0x180005178  mov     ebx, eax
0x18000517a  test    eax, eax
0x18000517c  jnz     loc_180005225
0x180005182  mov     r9d, 2011h; vt
0x180005188  cmp     word ptr [rbp+pvarg], r9w
0x18000518d  jz      short loc_1800051A6
0x18000518f  xor     r8d, r8d; wFlags
0x180005192  lea     rdx, [rbp+pvarg]; pvarSrc
0x180005196  lea     rcx, [rbp+pvarg]; pvargDest
0x18000519a  call    cs:__imp_VariantChangeType
0x1800051a0  mov     ebx, eax
0x1800051a2  test    eax, eax
0x1800051a4  jnz     short loc_180005225
0x1800051a6  mov     rdi, qword ptr [rbp+pvarg+8]
0x1800051aa  mov     rcx, rdi; psa
0x1800051ad  call    cs:__imp_SafeArrayGetDim
0x1800051b3  cmp     eax, 1
0x1800051b6  jz      short loc_1800051BF
0x1800051b8  mov     ebx, 80070057h
0x1800051bd  jmp     short loc_180005225
0x1800051bf  lea     r8, [rbp+plLbound]; plLbound
0x1800051c3  mov     edx, 1; nDim
0x1800051c8  mov     rcx, rdi; psa
0x1800051cb  call    cs:__imp_SafeArrayGetLBound
0x1800051d1  mov     ebx, eax
0x1800051d3  test    eax, eax
0x1800051d5  jnz     short loc_180005225
0x1800051d7  lea     r8, [rbp+plUbound]; plUbound
0x1800051db  mov     rcx, rdi; psa
0x1800051de  lea     edx, [rax+1]; nDim
0x1800051e1  call    cs:__imp_SafeArrayGetUBound
0x1800051e7  mov     ebx, eax
0x1800051e9  test    eax, eax
0x1800051eb  jnz     short loc_180005225
0x1800051ed  mov     esi, [rbp+plUbound]
0x1800051f0  sub     esi, [rbp+plLbound]
0x1800051f3  add     esi, 1
0x1800051f6  jz      short loc_180005225
0x1800051f8  lea     rdx, [rbp+ppvData]; ppvData
0x1800051fc  mov     rcx, rdi; psa
0x1800051ff  call    cs:__imp_SafeArrayAccessData
0x180005205  mov     ebx, eax
0x180005207  test    eax, eax
0x180005209  jnz     short loc_180005225
0x18000520b  mov     rax, [r14]
0x18000520e  mov     r8d, esi
0x180005211  mov     rdx, [rbp+ppvData]
0x180005215  mov     rcx, r14
0x180005218  mov     rax, [rax+0D0h]
0x18000521f  call    cs:__guard_dispatch_icall_fptr
0x180005225  cmp     [rbp+ppvData], 0
0x18000522a  jz      short loc_180005235
0x18000522c  mov     rcx, rdi; psa
0x18000522f  call    cs:__imp_SafeArrayUnaccessData
0x180005235  lea     rcx, [rbp+pvarg]; pvarg
0x180005239  call    cs:__imp_VariantClear
0x18000523f  mov     eax, ebx
0x180005241  add     rsp, 40h
0x180005245  pop     r14
0x180005247  pop     rdi
0x180005248  pop     rsi
0x180005249  pop     rbx
0x18000524a  pop     rbp
0x18000524b  retn
```
