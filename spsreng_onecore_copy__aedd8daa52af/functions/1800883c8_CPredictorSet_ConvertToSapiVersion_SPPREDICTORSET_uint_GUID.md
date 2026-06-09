# CPredictorSet::ConvertToSapiVersion(SPPREDICTORSET * *,uint,_GUID)

- ea: `0x1800883c8`
- end: `0x180088505`
- name: `?ConvertToSapiVersion@CPredictorSet@@QEAAJPEAPEAUSPPREDICTORSET@@IU_GUID@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CPredictorSet *__hidden this, struct SPPREDICTORSET **, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180077e44`

## callees

- `0x1800883c8`
- `0x18008853c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800884e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800884e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008844d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008844d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008840d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008840d`

## pseudocode

```c
__int64 __fastcall CPredictorSet::ConvertToSapiVersion(
        CPredictorSet *this,
        struct SPPREDICTORSET **a2,
        __int64 a3,
        struct _GUID *a4)
{
  _DWORD *v4; // rdi
  SIZE_T v8; // r14
  HRESULT Guid; // ebx
  unsigned __int64 v10; // r15
  _DWORD *v11; // r14
  __int64 v12; // rbp
  int v13; // edx
  float v15; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  v15 = 0.0;
  if ( !a2 || !*((_DWORD *)this + 3) )
  {
    Guid = -2147024809;
    goto LABEL_14;
  }
  v8 = (unsigned int)(32 * (*((_DWORD *)this + 2) + 2));
  v4 = CoTaskMemAlloc(v8);
  if ( !v4 )
  {
    Guid = -2147024882;
LABEL_14:
    CoTaskMemFree(v4);
    v4 = 0;
    goto LABEL_15;
  }
  v4[14] = *((_DWORD *)this + 2);
  *v4 = v8;
  *(_OWORD *)(v4 + 1) = xmmword_180113DA0;
  v4[13] = 1;
  *(struct _GUID *)(v4 + 9) = *a4;
  Guid = CoCreateGuid((GUID *)(v4 + 5));
  if ( Guid < 0 )
    goto LABEL_14;
  v10 = (unsigned __int64)v4 + v8;
  if ( v4 + 24 > (_DWORD *)((char *)v4 + v8) )
  {
LABEL_12:
    Guid = -2147467259;
    goto LABEL_14;
  }
  v4[15] = 64;
  v11 = v4 + 16;
  v12 = 0;
  while ( (unsigned int)v12 < *((_DWORD *)this + 2) )
  {
    if ( (unsigned __int64)(v11 + 8) > v10 )
      goto LABEL_12;
    Guid = CPredictorSet::GetElem(this, *((_WORD *)this + v12 + 272), 0, &v15);
    if ( Guid < 0 )
      goto LABEL_14;
    v12 = (unsigned int)(v12 + 1);
    v11[6] = LODWORD(v15);
    *v11 = v13;
    v11[4] = 10;
    v11[3] = 4;
    v11[2] = 1;
    v11 += 8;
  }
LABEL_15:
  *a2 = (struct SPPREDICTORSET *)v4;
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1800883c8  mov     rax, rsp
0x1800883cb  mov     [rax+18h], r8d
0x1800883cf  push    rbx
0x1800883d0  push    rbp
0x1800883d1  push    rsi
0x1800883d2  push    rdi
0x1800883d3  push    r12
0x1800883d5  push    r13
0x1800883d7  push    r14
0x1800883d9  push    r15
0x1800883db  sub     rsp, 28h
0x1800883df  xor     edi, edi
0x1800883e1  mov     rbx, r9
0x1800883e4  mov     [rax+18h], edi
0x1800883e7  mov     r13, rdx
0x1800883ea  mov     rsi, rcx
0x1800883ed  test    rdx, rdx
0x1800883f0  jz      loc_1800884DE
0x1800883f6  cmp     [rcx+0Ch], edi
0x1800883f9  jbe     loc_1800884DE
0x1800883ff  mov     eax, [rcx+8]
0x180088402  add     eax, 2
0x180088405  shl     eax, 5
0x180088408  mov     ecx, eax; cb
0x18008840a  mov     r14d, eax
0x18008840d  call    cs:__imp_CoTaskMemAlloc
0x180088413  mov     rdi, rax
0x180088416  test    rax, rax
0x180088419  jnz     short loc_180088425
0x18008841b  mov     ebx, 8007000Eh
0x180088420  jmp     loc_1800884E3
0x180088425  mov     eax, [rsi+8]
0x180088428  lea     rcx, [rdi+14h]; pguid
0x18008842c  movups  xmm0, cs:xmmword_180113DA0
0x180088433  mov     [rdi+38h], eax
0x180088436  mov     [rdi], r14d
0x180088439  movdqu  xmmword ptr [rdi+4], xmm0
0x18008843e  mov     dword ptr [rdi+34h], 1
0x180088445  movaps  xmm0, xmmword ptr [rbx]
0x180088448  movdqu  xmmword ptr [rdi+24h], xmm0
0x18008844d  call    cs:__imp_CoCreateGuid
0x180088453  mov     ebx, eax
0x180088455  test    eax, eax
0x180088457  js      loc_1800884E3
0x18008845d  lea     r15, [r14+rdi]
0x180088461  lea     rcx, [rdi+60h]
0x180088465  cmp     rcx, r15
0x180088468  ja      short loc_1800884D7
0x18008846a  mov     dword ptr [rdi+3Ch], 40h ; '@'
0x180088471  lea     r14, [rdi+40h]
0x180088475  xor     ebp, ebp
0x180088477  cmp     ebp, [rsi+8]
0x18008847a  jnb     short loc_1800884EE
0x18008847c  lea     r12, [r14+20h]
0x180088480  cmp     r12, r15
0x180088483  ja      short loc_1800884D7
0x180088485  movsx   edx, word ptr [rsi+rbp*2+220h]; __int16
0x18008848d  lea     r9, [rsp+68h+arg_10]; float *
0x180088495  xor     r8d, r8d; unsigned int
0x180088498  mov     rcx, rsi; this
0x18008849b  call    ?GetElem@CPredictorSet@@QEAAJFIPEAM@Z; CPredictorSet::GetElem(short,uint,float *)
0x1800884a0  mov     ebx, eax
0x1800884a2  test    eax, eax
0x1800884a4  js      short loc_1800884E3
0x1800884a6  movss   xmm0, [rsp+68h+arg_10]
0x1800884af  inc     ebp
0x1800884b1  movss   dword ptr [r14+18h], xmm0
0x1800884b7  mov     [r14], edx
0x1800884ba  mov     dword ptr [r14+10h], 0Ah
0x1800884c2  mov     dword ptr [r14+0Ch], 4
0x1800884ca  mov     dword ptr [r14+8], 1
0x1800884d2  mov     r14, r12
0x1800884d5  jmp     short loc_180088477
0x1800884d7  mov     ebx, 80004005h
0x1800884dc  jmp     short loc_1800884E3
0x1800884de  mov     ebx, 80070057h
0x1800884e3  mov     rcx, rdi; pv
0x1800884e6  call    cs:__imp_CoTaskMemFree
0x1800884ec  xor     edi, edi
0x1800884ee  mov     [r13+0], rdi
0x1800884f2  mov     eax, ebx
0x1800884f4  add     rsp, 28h
0x1800884f8  pop     r15
0x1800884fa  pop     r14
0x1800884fc  pop     r13
0x1800884fe  pop     r12
0x180088500  pop     rdi
0x180088501  pop     rsi
0x180088502  pop     rbp
0x180088503  pop     rbx
0x180088504  retn
```
