# CASFStreamSelector::CreatePrioritizedStreamInfos(void)

- ea: `0x1800354f0`
- end: `0x1800357c1`
- name: `?CreatePrioritizedStreamInfos@CASFStreamSelector@@IEAAJXZ`
- size: `721`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039510`

## callees

- `0x180001174`
- `0x1800015d0`
- `0x180030a00`
- `0x1800310c0`
- `0x180031570`
- `0x180033484`
- `0x180033b30`
- `0x180033d6c`
- `0x1800354f0`
- `0x18003f294`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::CreatePrioritizedStreamInfos(CASFStreamSelector *this)
{
  __int64 v2; // rcx
  __int64 result; // rax
  int v4; // ebx
  unsigned __int16 i; // di
  __int64 v6; // rbx
  __int64 v7; // rdx
  CASFStreamSelector::STREAM_INFO *v8; // rax
  __int64 v9; // rax
  CASFStreamSelector::STREAM_INFO *v10; // rbx
  char v11; // al
  unsigned int v12; // edx
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v17; // [rsp+4Ch] [rbp-B4h] BYREF
  _WORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+54h] [rbp-ACh] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v21; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 Buf2; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[512]; // [rsp+70h] [rbp-90h] BYREF

  v15 = 0;
  v2 = *((_QWORD *)this + 3);
  v14 = 0;
  result = ASFGetHeaderObject(v2, &CLSID_ASFLanguageListObject, &IID_IASFLanguageListObject, &v14);
  if ( (int)result >= 0 )
  {
    v4 = ASFFindHeaderObject(*((_QWORD *)this + 3), &CLSID_ASFPrioritizationObject, &IID_IASFPrioritizationObject, &v15);
    if ( v4 < 0 )
    {
      v4 = 0;
    }
    else
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v15 + 80LL))(v15, &v17);
      for ( i = 0; i < v17; ++i )
      {
        v16[0] = 0;
        v19 = 0;
        v13 = 0;
        v20 = 0;
        v18[0] = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, _WORD *, __int16 *))(*(_QWORD *)v15 + 88LL))(v15, i, v16, &v19) >= 0
          && (int)ASFGetStreamPropertiesObject(*((_QWORD *)this + 3), v16[0], &v13) >= 0 )
        {
          v6 = v13;
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 128LL))(v13, &v20);
          LOBYTE(v7) = -1;
          (*(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v6 + 320LL))(v6, v7, v23);
          (*(void (__fastcall **)(__int64, _BYTE *, _WORD *))(*(_QWORD *)v14 + 120LL))(v14, v23, v18);
          Buf2 = 0;
          (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v6 + 80LL))(v6, &Buf2);
          v21 = 0;
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 240LL))(v6, &v21);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          v8 = (CASFStreamSelector::STREAM_INFO *)operator new(0x110u);
          if ( !v8 )
            goto LABEL_12;
          v9 = CASFStreamSelector::STREAM_INFO::STREAM_INFO(v8);
          v10 = (CASFStreamSelector::STREAM_INFO *)v9;
          if ( !v9 )
            goto LABEL_12;
          *(_WORD *)v9 = v16[0];
          *(_DWORD *)(v9 + 4) = v20;
          *(_WORD *)(v9 + 2) = v18[0];
          *(_DWORD *)(v9 + 8) = v21 >> 31 == 0;
          *(_DWORD *)(v9 + 12) = memcmp_0(&CLSID_ASFVideoMedia, &Buf2, 0x10u) == 0;
          *((_DWORD *)v10 + 4) = 0;
          v11 = v19 & 1;
          *((_DWORD *)v10 + 6) = 0;
          *((_DWORD *)v10 + 5) = v11 != 0 ? 2 : 1000;
          if ( !(unsigned int)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::Add((char *)this + 64, v10) )
          {
            CASFStreamSelector::STREAM_INFO::`scalar deleting destructor'(v10, v12);
LABEL_12:
            v4 = -2147024882;
            break;
          }
        }
        v4 = 0;
      }
    }
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800354f0  mov     [rsp-8+arg_8], rbx
0x1800354f5  mov     [rsp-8+arg_10], rsi
0x1800354fa  push    rbp
0x1800354fb  push    rdi
0x1800354fc  push    r15
0x1800354fe  lea     rbp, [rsp-180h]
0x180035506  sub     rsp, 280h
0x18003550d  mov     rax, cs:__security_cookie
0x180035514  xor     rax, rsp
0x180035517  mov     [rbp+190h+var_20], rax
0x18003551e  mov     rsi, rcx
0x180035521  mov     [rsp+290h+var_250], 0
0x18003552a  mov     rcx, [rcx+18h]
0x18003552e  lea     r9, [rsp+290h+var_258]
0x180035533  lea     r8, IID_IASFLanguageListObject
0x18003553a  mov     [rsp+290h+var_258], 0
0x180035543  lea     rdx, CLSID_ASFLanguageListObject
0x18003554a  call    ASFGetHeaderObject
0x18003554f  test    eax, eax
0x180035551  js      loc_18003579A
0x180035557  mov     rcx, [rsi+18h]
0x18003555b  lea     r9, [rsp+290h+var_250]
0x180035560  lea     r8, IID_IASFPrioritizationObject
0x180035567  lea     rdx, CLSID_ASFPrioritizationObject
0x18003556e  call    ASFFindHeaderObject
0x180035573  mov     ebx, eax
0x180035575  test    eax, eax
0x180035577  js      loc_180035761
0x18003557d  xor     ecx, ecx
0x18003557f  mov     [rsp+290h+var_244], cx
0x180035584  mov     rcx, [rsp+290h+var_250]
0x180035589  mov     rdx, [rcx]
0x18003558c  mov     rax, [rdx+50h]
0x180035590  lea     rdx, [rsp+290h+var_244]
0x180035595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003559a  xor     edi, edi
0x18003559c  lea     r15d, [rdi+1]
0x1800355a0  cmp     di, [rsp+290h+var_244]
0x1800355a5  jnb     loc_180035763
0x1800355ab  mov     rcx, [rsp+290h+var_250]
0x1800355b0  lea     r9, [rsp+290h+var_23C]
0x1800355b5  xor     eax, eax
0x1800355b7  lea     r8, [rsp+290h+var_248]
0x1800355bc  mov     [rsp+290h+var_248], ax
0x1800355c1  movzx   edx, di
0x1800355c4  mov     [rsp+290h+var_23C], ax
0x1800355c9  mov     [rsp+290h+var_260], rax
0x1800355ce  mov     [rsp+290h+var_238], eax
0x1800355d2  mov     [rsp+290h+var_240], ax
0x1800355d7  mov     rax, [rcx]
0x1800355da  mov     rax, [rax+58h]
0x1800355de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355e3  test    eax, eax
0x1800355e5  js      loc_180035747
0x1800355eb  movzx   edx, [rsp+290h+var_248]
0x1800355f0  lea     r8, [rsp+290h+var_260]
0x1800355f5  mov     rcx, [rsi+18h]
0x1800355f9  call    ASFGetStreamPropertiesObject
0x1800355fe  test    eax, eax
0x180035600  js      loc_180035747
0x180035606  mov     rbx, [rsp+290h+var_260]
0x18003560b  lea     rdx, [rsp+290h+var_238]
0x180035610  mov     rcx, rbx
0x180035613  mov     rax, [rbx]
0x180035616  mov     rax, [rax+80h]
0x18003561d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035622  mov     rax, [rbx]
0x180035625  lea     r8, [rsp+290h+var_220]
0x18003562a  mov     dl, 0FFh
0x18003562c  mov     rcx, rbx
0x18003562f  mov     rax, [rax+140h]
0x180035636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003563b  mov     rcx, [rsp+290h+var_258]
0x180035640  lea     r8, [rsp+290h+var_240]
0x180035645  lea     rdx, [rsp+290h+var_220]
0x18003564a  mov     rax, [rcx]
0x18003564d  mov     rax, [rax+78h]
0x180035651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035656  xorps   xmm0, xmm0
0x180035659  lea     rdx, [rsp+290h+Buf2]
0x18003565e  movups  [rsp+290h+Buf2], xmm0
0x180035663  mov     rax, [rbx]
0x180035666  mov     rcx, rbx
0x180035669  mov     rax, [rax+50h]
0x18003566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035672  mov     [rsp+290h+var_234], 0
0x18003567a  lea     rdx, [rsp+290h+var_234]
0x18003567f  mov     rax, [rbx]
0x180035682  mov     rcx, rbx
0x180035685  mov     rax, [rax+0F0h]
0x18003568c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035691  mov     rax, [rbx]
0x180035694  mov     rcx, rbx
0x180035697  mov     rax, [rax+10h]
0x18003569b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356a0  mov     ecx, 110h; Size
0x1800356a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800356aa  test    rax, rax
0x1800356ad  jz      loc_18003575A
0x1800356b3  mov     rcx, rax; this
0x1800356b6  call    ??0STREAM_INFO@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_INFO::STREAM_INFO(void)
0x1800356bb  mov     rbx, rax
0x1800356be  test    rax, rax
0x1800356c1  jz      loc_18003575A
0x1800356c7  movzx   ecx, [rsp+290h+var_248]
0x1800356cc  lea     rdx, [rsp+290h+Buf2]; Buf2
0x1800356d1  mov     [rax], cx
0x1800356d4  mov     r8d, 10h; Size
0x1800356da  mov     ecx, [rsp+290h+var_238]
0x1800356de  mov     [rax+4], ecx
0x1800356e1  movzx   ecx, [rsp+290h+var_240]
0x1800356e6  mov     [rax+2], cx
0x1800356ea  mov     ecx, [rsp+290h+var_234]
0x1800356ee  shr     ecx, 1Fh
0x1800356f1  not     ecx
0x1800356f3  and     ecx, r15d
0x1800356f6  mov     [rax+8], ecx
0x1800356f9  lea     rcx, CLSID_ASFVideoMedia; Buf1
0x180035700  call    memcmp_0
0x180035705  xor     ecx, ecx
0x180035707  mov     rdx, rbx
0x18003570a  test    eax, eax
0x18003570c  setz    cl
0x18003570f  mov     [rbx+0Ch], ecx
0x180035712  mov     dword ptr [rbx+10h], 0
0x180035719  mov     al, byte ptr [rsp+290h+var_23C]
0x18003571d  and     al, r15b
0x180035720  mov     dword ptr [rbx+18h], 0
0x180035727  neg     al
0x180035729  sbb     ecx, ecx
0x18003572b  and     ecx, 0FFFFFC1Ah
0x180035731  add     ecx, 3E8h
0x180035737  mov     [rbx+14h], ecx
0x18003573a  lea     rcx, [rsi+40h]
0x18003573e  call    ?Add@?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEAAHPEAUSTREAM_INFO@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::Add(CASFStreamSelector::STREAM_INFO *,ulong *)
0x180035743  test    eax, eax
0x180035745  jz      short loc_180035752
0x180035747  xor     ebx, ebx
0x180035749  add     di, r15w
0x18003574d  jmp     loc_1800355A0
0x180035752  mov     rcx, rbx; this
0x180035755  call    ??_GSTREAM_INFO@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::STREAM_INFO::`scalar deleting destructor'(uint)
0x18003575a  mov     ebx, 8007000Eh
0x18003575f  jmp     short loc_180035763
0x180035761  xor     ebx, ebx
0x180035763  mov     rcx, [rsp+290h+var_258]
0x180035768  test    rcx, rcx
0x18003576b  jz      short loc_180035782
0x18003576d  mov     rax, [rcx]
0x180035770  mov     rax, [rax+10h]
0x180035774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035779  mov     [rsp+290h+var_258], 0
0x180035782  mov     rcx, [rsp+290h+var_250]
0x180035787  test    rcx, rcx
0x18003578a  jz      short loc_180035798
0x18003578c  mov     rax, [rcx]
0x18003578f  mov     rax, [rax+10h]
0x180035793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035798  mov     eax, ebx
0x18003579a  mov     rcx, [rbp+190h+var_20]
0x1800357a1  xor     rcx, rsp; StackCookie
0x1800357a4  call    __security_check_cookie
0x1800357a9  lea     r11, [rsp+290h+var_10]
0x1800357b1  mov     rbx, [r11+28h]
0x1800357b5  mov     rsi, [r11+30h]
0x1800357b9  mov     rsp, r11
0x1800357bc  pop     r15
0x1800357be  pop     rdi
0x1800357bf  pop     rbp
0x1800357c0  retn
```
