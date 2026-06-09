# FindHandler___FrameHandler4_

- ea: `0x140003624`
- end: `0x140003b5b`
- name: `FindHandler___FrameHandler4_`
- size: `1335`
- prototype: `__int64 __usercall@<rax>(struct EHExceptionRecord *@<rcx>, struct FH4::FuncInfo4 *, char, int, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400040e0`

## callees

- `0x140001500`
- `0x1400024d8`
- `0x140002544`
- `0x140002a98`
- `0x140002ad0`
- `0x140002bc0`
- `0x140003008`
- `0x140003178`
- `0x140003540`
- `0x140003624`
- `0x140003b64`
- `0x140003f98`
- `0x1400043e0`
- `0x140004468`
- `0x140004598`
- `0x1400048bc`
- `0x140004e34`
- `0x140004f24`
- `0x140005504`
- `0x1400056be`
- `0x1400056fa`

## pseudocode

```c
__int64 __fastcall FindHandler___FrameHandler4_(
        struct EHExceptionRecord *a1,
        unsigned __int64 *a2,
        __int64 a3,
        __int64 a4,
        struct FH4::FuncInfo4 *a5,
        char a6,
        int a7,
        __int64 a8)
{
  int v10; // esi
  _BYTE *v11; // rdx
  __int64 v12; // rcx
  _BYTE *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  unsigned int magicNumber; // eax
  __int64 result; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rdx
  _BYTE *v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  unsigned int v39; // eax
  unsigned int v40; // r12d
  __int64 v41; // rbx
  ThrowInfo *pThrowInfo; // rax
  __int64 pCatchableTypeArray; // r13
  int *v44; // r13
  __int64 v45; // rbx
  int i; // r12d
  __int64 v47; // rbx
  __int64 v48; // rbx
  _BYTE *v49; // r10
  __int64 v50; // rcx
  __int64 v51; // r9
  unsigned int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  unsigned int *v55; // r10
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  int v59; // [rsp+50h] [rbp-B0h]
  char v60; // [rsp+60h] [rbp-A0h]
  __int32 v61; // [rsp+64h] [rbp-9Ch]
  int v62; // [rsp+68h] [rbp-98h]
  int v64; // [rsp+78h] [rbp-88h]
  __int64 v65; // [rsp+80h] [rbp-80h]
  __m128i pExceptionObject; // [rsp+88h] [rbp-78h] BYREF
  int v67[2]; // [rsp+A0h] [rbp-60h]
  unsigned __int64 *v68; // [rsp+A8h] [rbp-58h]
  __m128i v69; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v70; // [rsp+C8h] [rbp-38h]
  _OWORD v71[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v72; // [rsp+F0h] [rbp-10h]
  _DWORD v73[10]; // [rsp+F8h] [rbp-8h] BYREF
  _DWORD v74[6]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v75; // [rsp+138h] [rbp+38h]
  __int128 v76; // [rsp+148h] [rbp+48h]
  __int64 v77; // [rsp+158h] [rbp+58h]

  v68 = a2;
  *(_QWORD *)v67 = a8;
  v60 = 0;
  v10 = __FrameHandler4::StateFromControlPc(a5, (struct _xDISPATCHER_CONTEXT *)a4);
  if ( *(_DWORD *)(a4 + 72) )
  {
    if ( *(_DWORD *)(((__int64 (*)(void))_vcrt_getptd)() + 120) != -2 )
      goto LABEL_56;
    v10 = *(_DWORD *)(a4 + 72) - 2;
  }
  else if ( *(_DWORD *)(((__int64 (*)(void))_vcrt_getptd)() + 120) != -2 )
  {
    v10 = *(_DWORD *)(((__int64 (*)(void))_vcrt_getptd)() + 120);
    *(_DWORD *)(((__int64 (*)(void))_vcrt_getptd)() + 120) = -2;
  }
  if ( v10 < -1 )
    goto LABEL_56;
  if ( *((_DWORD *)a5 + 2) )
  {
    v13 = (_BYTE *)(*((int *)a5 + 2) + *(_QWORD *)(a4 + 8));
    v12 = *v13 & 0xF;
    v14 = *((char *)&FH4::s_negLengthTab + v12);
    LOBYTE(v12) = *((_BYTE *)&FH4::s_shiftTab + v12);
    v11 = &v13[-v14];
    v15 = *((_DWORD *)v11 - 1) >> v12;
  }
  else
  {
    v15 = 0;
  }
  if ( v10 >= v15 )
    goto LABEL_56;
  if ( a1->ExceptionCode == -529697949 && a1->NumberParameters == 4 )
  {
    magicNumber = a1->params.magicNumber;
    if ( (magicNumber == 429065504 || magicNumber - 429065505 <= 1) && !a1->params.pThrowInfo )
    {
      result = _vcrt_getptd(v12, v11, 0x140000000uLL);
      if ( !*(_QWORD *)(result + 32) )
        return result;
      a1 = *(struct EHExceptionRecord **)(_vcrt_getptd(v19, v18, v20) + 32);
      v60 = 1;
      a3 = *(_QWORD *)(_vcrt_getptd(v22, v21, v23) + 40);
      SetThrowImageBase(a1->params.pThrowImageBase);
      if ( !a1 )
        goto LABEL_56;
      if ( a1->ExceptionCode == -529697949 && a1->NumberParameters == 4 )
      {
        v27 = a1->params.magicNumber;
        if ( (v27 == 429065504 || v27 - 429065505 <= 1) && !a1->params.pThrowInfo )
          goto LABEL_56;
      }
      if ( *(_QWORD *)(_vcrt_getptd(v25, v24, v26) + 56) )
      {
        v31 = *(_QWORD *)(_vcrt_getptd(v29, v28, v30) + 56);
        *(_QWORD *)(_vcrt_getptd(v33, v32, v34) + 56) = 0;
        if ( !(unsigned __int8)IsInExceptionSpec(a1, v31) )
        {
          if ( (unsigned __int8)Is_bad_exception_allowed(v31) )
          {
            LOBYTE(v35) = 1;
            _DestructExceptionObject(a1, v35);
            std::bad_exception::bad_exception((std::bad_exception *)&pExceptionObject);
            throw (std::bad_exception *)&pExceptionObject;
          }
          o_terminate_0();
          __debugbreak();
        }
      }
    }
  }
  FH4::TryBlockMap4::TryBlockMap4((FH4::TryBlockMap4 *)v73, a5, *(_QWORD *)(a4 + 8));
  if ( a1->ExceptionCode == -529697949
    && a1->NumberParameters == 4
    && ((v39 = a1->params.magicNumber, v39 == 429065504) || v39 - 429065505 <= 1) )
  {
    if ( v73[0] )
    {
      __FrameHandler4::GetRangeOfTrysToCheck(&v69, v73, (unsigned int)v10, a4, a5, a7);
      pExceptionObject = v69;
      if ( _mm_cvtsi128_si32(_mm_srli_si128(v69, 8)) < v70 )
      {
        v40 = pExceptionObject.m128i_u32[2];
        v41 = v69.m128i_i64[0];
        v61 = pExceptionObject.m128i_i32[2];
        v65 = v69.m128i_i64[0];
        do
        {
          pExceptionObject = *(__m128i *)(v41 + 24);
          if ( pExceptionObject.m128i_i32[0] <= v10 && v10 <= pExceptionObject.m128i_i32[1] )
          {
            FH4::HandlerMap4::HandlerMap4(
              (FH4::HandlerMap4 *)v74,
              (const struct FH4::TryBlockMapEntry4 *)&pExceptionObject,
              *(_QWORD *)(a4 + 8),
              **(_DWORD **)(a4 + 16));
            v62 = 0;
            v64 = v74[0];
            if ( v74[0] )
            {
              while ( 2 )
              {
                pThrowInfo = a1->params.pThrowInfo;
                v71[0] = v75;
                v72 = v77;
                v71[1] = v76;
                pCatchableTypeArray = pThrowInfo->pCatchableTypeArray;
                v44 = (int *)(GetThrowImageBase() + 4 + pCatchableTypeArray);
                v45 = a1->params.pThrowInfo->pCatchableTypeArray;
                for ( i = *(_DWORD *)(GetThrowImageBase() + v45); i > 0; --i )
                {
                  v47 = *v44;
                  v48 = GetThrowImageBase() + v47;
                  if ( (unsigned int)TypeMatchHelper<__FrameHandler4>(v71, v48, a1->params.pThrowInfo) )
                  {
                    LOBYTE(v59) = v60;
                    CatchIt___FrameHandler4_(
                      a1,
                      v68,
                      a5,
                      (struct FH4::HandlerType4 *)v71,
                      v48,
                      (__int64)&pExceptionObject,
                      a7,
                      v67[0],
                      v59,
                      a6);
                    goto LABEL_44;
                  }
                  ++v44;
                }
                FH4::HandlerMap4::DecompHandler((FH4::HandlerMap4 *)v74);
                if ( ++v62 != v64 )
                  continue;
                break;
              }
LABEL_44:
              v40 = v61;
              v41 = v65;
            }
          }
          v49 = *(_BYTE **)(v41 + 8);
          v61 = ++v40;
          v50 = *v49 & 0xF;
          v51 = *((char *)&FH4::s_negLengthTab + v50);
          LOBYTE(v50) = *((_BYTE *)&FH4::s_shiftTab + v50);
          v52 = *(_DWORD *)&v49[-v51 - 4];
          *(_QWORD *)(v41 + 8) = &v49[-v51];
          *(_DWORD *)(v41 + 24) = v52 >> v50;
          v53 = v49[-v51] & 0xF;
          v38 = *((char *)&FH4::s_negLengthTab + v53);
          v36 = &v49[-v38 - v51];
          *(_DWORD *)(v41 + 28) = *((_DWORD *)v36 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v53);
          *(_QWORD *)(v41 + 8) = v36;
          v54 = *v36 & 0xF;
          v55 = (unsigned int *)&v49[-*((char *)&FH4::s_negLengthTab + v54) - v38 - v51];
          *(_DWORD *)(v41 + 32) = *(v55 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v54);
          *(_QWORD *)(v41 + 8) = v55;
          v37 = *v55;
          *(_QWORD *)(v41 + 8) = v55 + 1;
          *(_DWORD *)(v41 + 36) = v37;
        }
        while ( v40 < v70 );
      }
    }
    if ( (*(_BYTE *)a5 & 0x40) != 0 && !__FrameHandler4::ExecutionInCatch((struct _xDISPATCHER_CONTEXT *)a4, a5) )
    {
      *(_QWORD *)(_vcrt_getptd(v37, v36, v38) + 32) = a1;
      *(_QWORD *)(_vcrt_getptd(v57, v56, v58) + 40) = a3;
      o_terminate_0();
      __debugbreak();
    }
  }
  else if ( v73[0] )
  {
    if ( a6 )
      goto LABEL_56;
    FindHandlerForForeignException___FrameHandler4_(a1, a5, v10, a7, a8);
  }
  result = _vcrt_getptd(v37, v36, v38);
  if ( *(_QWORD *)(result + 56) )
LABEL_56:
    abort();
  return result;
}

```

## disassembly

```asm
0x140003624  push    rbp
0x140003626  push    rbx
0x140003627  push    rsi
0x140003628  push    rdi
0x140003629  push    r12
0x14000362b  push    r13
0x14000362d  push    r14
0x14000362f  push    r15
0x140003631  lea     rbp, [rsp-88h]
0x140003639  sub     rsp, 188h
0x140003640  mov     rax, cs:__security_cookie
0x140003647  xor     rax, rsp
0x14000364a  mov     [rbp+0C0h+var_50], rax
0x14000364e  mov     r15, [rbp+0C0h+arg_20]
0x140003655  mov     rbx, r8
0x140003658  mov     r13, [rbp+0C0h+arg_38]
0x14000365f  mov     r12, rdx
0x140003662  mov     [rbp+0C0h+var_118], rdx
0x140003666  mov     rdi, rcx
0x140003669  mov     rcx, r15; struct FH4::FuncInfo4 *
0x14000366c  mov     [rsp+1C0h+var_150], rbx
0x140003671  mov     rdx, r9; struct _xDISPATCHER_CONTEXT *
0x140003674  mov     qword ptr [rbp+0C0h+var_120], r13
0x140003678  mov     r14, r9
0x14000367b  mov     byte ptr [rsp+1C0h+var_160], 0
0x140003680  call    ?StateFromControlPc@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler4::StateFromControlPc(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *)
0x140003685  cmp     dword ptr [r14+48h], 0
0x14000368a  mov     esi, eax
0x14000368c  jz      short loc_1400036A6
0x14000368e  call    __vcrt_getptd
0x140003693  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x140003697  jnz     loc_140003B55
0x14000369d  mov     esi, [r14+48h]
0x1400036a1  sub     esi, 2
0x1400036a4  jmp     short loc_1400036C5
0x1400036a6  call    __vcrt_getptd
0x1400036ab  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x1400036af  jz      short loc_1400036C5
0x1400036b1  call    __vcrt_getptd
0x1400036b6  mov     esi, [rax+78h]
0x1400036b9  call    __vcrt_getptd
0x1400036be  mov     dword ptr [rax+78h], 0FFFFFFFEh
0x1400036c5  cmp     esi, 0FFFFFFFFh
0x1400036c8  jl      loc_140003B55
0x1400036ce  cmp     dword ptr [r15+8], 0
0x1400036d3  lea     r8, cs:140000000h
0x1400036da  jz      short loc_140003708
0x1400036dc  movsxd  rcx, dword ptr [r15+8]
0x1400036e0  mov     rdx, [r14+8]
0x1400036e4  add     rdx, rcx
0x1400036e7  movzx   ecx, byte ptr [rdx]
0x1400036ea  and     ecx, 0Fh
0x1400036ed  movsx   rax, byte ptr [rcx+r8+7460h]
0x1400036f6  mov     cl, [rcx+r8+7470h]
0x1400036fe  sub     rdx, rax
0x140003701  mov     eax, [rdx-4]
0x140003704  shr     eax, cl
0x140003706  jmp     short loc_14000370A
0x140003708  xor     eax, eax
0x14000370a  cmp     esi, eax
0x14000370c  jge     loc_140003B55
0x140003712  cmp     dword ptr [rdi], 0E06D7363h
0x140003718  jnz     loc_140003801
0x14000371e  cmp     dword ptr [rdi+18h], 4
0x140003722  jnz     loc_140003801
0x140003728  mov     eax, [rdi+20h]
0x14000372b  cmp     eax, 19930520h
0x140003730  jz      short loc_140003740
0x140003732  add     eax, 0E66CFADFh
0x140003737  cmp     eax, 1
0x14000373a  ja      loc_140003801
0x140003740  cmp     qword ptr [rdi+30h], 0
0x140003745  jnz     loc_140003801
0x14000374b  call    __vcrt_getptd
0x140003750  cmp     qword ptr [rax+20h], 0
0x140003755  jz      loc_140003AEE
0x14000375b  call    __vcrt_getptd
0x140003760  mov     rdi, [rax+20h]
0x140003764  call    __vcrt_getptd
0x140003769  mov     rcx, [rdi+38h]
0x14000376d  mov     byte ptr [rsp+1C0h+var_160], 1
0x140003772  mov     rbx, [rax+28h]
0x140003776  mov     [rsp+1C0h+var_150], rbx
0x14000377b  call    _SetThrowImageBase
0x140003780  test    rdi, rdi
0x140003783  jz      loc_140003B55
0x140003789  cmp     dword ptr [rdi], 0E06D7363h
0x14000378f  jnz     short loc_1400037B6
0x140003791  cmp     dword ptr [rdi+18h], 4
0x140003795  jnz     short loc_1400037B6
0x140003797  mov     eax, [rdi+20h]
0x14000379a  cmp     eax, 19930520h
0x14000379f  jz      short loc_1400037AB
0x1400037a1  add     eax, 0E66CFADFh
0x1400037a6  cmp     eax, 1
0x1400037a9  ja      short loc_1400037B6
0x1400037ab  cmp     qword ptr [rdi+30h], 0
0x1400037b0  jz      loc_140003B55
0x1400037b6  call    __vcrt_getptd
0x1400037bb  cmp     qword ptr [rax+38h], 0
0x1400037c0  jz      short loc_140003801
0x1400037c2  call    __vcrt_getptd
0x1400037c7  mov     rbx, [rax+38h]
0x1400037cb  call    __vcrt_getptd
0x1400037d0  mov     rdx, rbx
0x1400037d3  mov     rcx, rdi
0x1400037d6  mov     qword ptr [rax+38h], 0
0x1400037de  call    IsInExceptionSpec
0x1400037e3  test    al, al
0x1400037e5  jnz     short loc_1400037FC
0x1400037e7  mov     rcx, rbx
0x1400037ea  call    Is_bad_exception_allowed
0x1400037ef  test    al, al
0x1400037f1  jz      loc_140003B32
0x1400037f7  jmp     loc_140003B0E
0x1400037fc  mov     rbx, [rsp+1C0h+var_150]
0x140003801  mov     r8, [r14+8]; unsigned __int64
0x140003805  lea     rcx, [rbp+0C0h+var_C8]; this
0x140003809  mov     rdx, r15; struct FH4::FuncInfo4 *
0x14000380c  call    ??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z; FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)
0x140003811  cmp     dword ptr [rdi], 0E06D7363h
0x140003817  jnz     loc_140003AA6
0x14000381d  cmp     dword ptr [rdi+18h], 4
0x140003821  jnz     loc_140003AA6
0x140003827  mov     eax, [rdi+20h]
0x14000382a  cmp     eax, 19930520h
0x14000382f  jz      short loc_14000383F
0x140003831  add     eax, 0E66CFADFh
0x140003836  cmp     eax, 1
0x140003839  ja      loc_140003AA6
0x14000383f  cmp     [rbp+0C0h+var_C8], 0
0x140003843  jbe     loc_140003A8B
0x140003849  mov     eax, [rbp+0C0h+arg_30]
0x14000384f  lea     rdx, [rbp+0C0h+var_C8]
0x140003853  mov     dword ptr [rsp+1C0h+var_198], eax
0x140003857  lea     rcx, [rbp+0C0h+var_110]
0x14000385b  mov     r9, r14
0x14000385e  mov     [rsp+1C0h+var_1A0], r15
0x140003863  mov     r8d, esi
0x140003866  call    ?GetRangeOfTrysToCheck@__FrameHandler4@@SA?AU?$pair@Viterator@TryBlockMap4@FH4@@V123@@std@@AEAVTryBlockMap4@FH4@@HPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@5@H@Z; __FrameHandler4::GetRangeOfTrysToCheck(FH4::TryBlockMap4 &,int,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)
0x14000386b  movups  xmm1, [rbp+0C0h+var_110]
0x14000386f  movdqa  xmm0, xmm1
0x140003873  psrldq  xmm0, 8
0x140003878  movd    eax, xmm0
0x14000387c  movdqu  [rbp+0C0h+pExceptionObject], xmm1
0x140003881  cmp     eax, [rbp+0C0h+var_F8]
0x140003884  jnb     loc_140003A8B
0x14000388a  mov     r12d, dword ptr [rbp+0C0h+pExceptionObject+8]
0x14000388e  lea     r11, cs:140000000h
0x140003895  movq    rbx, xmm1
0x14000389a  mov     [rsp+1C0h+var_15C], r12d
0x14000389f  mov     [rbp+0C0h+var_140], rbx
0x1400038a3  movups  xmm0, xmmword ptr [rbx+18h]
0x1400038a7  movq    rax, xmm0
0x1400038ac  movups  [rbp+0C0h+pExceptionObject], xmm0
0x1400038b0  cmp     eax, esi
0x1400038b2  jg      loc_1400039E4
0x1400038b8  shr     rax, 20h
0x1400038bc  cmp     esi, eax
0x1400038be  jg      loc_1400039E4
0x1400038c4  mov     r9, [r14+10h]
0x1400038c8  lea     rdx, [rbp+0C0h+pExceptionObject]; struct FH4::TryBlockMapEntry4 *
0x1400038cc  mov     r8, [r14+8]; unsigned __int64
0x1400038d0  lea     rcx, [rbp+0C0h+var_A0]; this
0x1400038d4  mov     r9d, [r9]; int
0x1400038d7  call    ??0HandlerMap4@FH4@@QEAA@PEBUTryBlockMapEntry4@1@_KH@Z; FH4::HandlerMap4::HandlerMap4(FH4::TryBlockMapEntry4 const *,unsigned __int64,int)
0x1400038dc  mov     eax, [rbp+0C0h+var_A0]
0x1400038df  mov     [rsp+1C0h+var_158], 0
0x1400038e7  mov     [rsp+1C0h+var_148], eax
0x1400038eb  test    eax, eax
0x1400038ed  jz      loc_1400039DD
0x1400038f3  movups  xmm0, [rbp+0C0h+var_88]
0x1400038f7  mov     rax, [rdi+30h]
0x1400038fb  movups  xmm1, [rbp+0C0h+var_78]
0x1400038ff  movups  [rbp+0C0h+var_F0], xmm0
0x140003903  movsd   xmm0, [rbp+0C0h+var_68]
0x140003908  movsd   [rbp+0C0h+var_D0], xmm0
0x14000390d  movups  [rbp+0C0h+var_E0], xmm1
0x140003911  movsxd  r13, dword ptr [rax+0Ch]
0x140003915  call    _GetThrowImageBase
0x14000391a  add     rax, 4
0x14000391e  add     r13, rax
0x140003921  mov     rax, [rdi+30h]
0x140003925  movsxd  rbx, dword ptr [rax+0Ch]
0x140003929  call    _GetThrowImageBase
0x14000392e  mov     r12d, [rax+rbx]
0x140003932  jmp     short loc_14000395B
0x140003934  movsxd  rbx, dword ptr [r13+0]
0x140003938  call    _GetThrowImageBase
0x14000393d  mov     r8, [rdi+30h]
0x140003941  lea     rcx, [rbp+0C0h+var_F0]
0x140003945  add     rbx, rax
0x140003948  mov     rdx, rbx
0x14000394b  call    ??$TypeMatchHelper@V__FrameHandler4@@@@YAHPEAUHandlerType4@FH4@@PEBU_s_CatchableType@@PEBU_s_ThrowInfo@@@Z; TypeMatchHelper<__FrameHandler4>(FH4::HandlerType4 *,_s_CatchableType const *,_s_ThrowInfo const *)
0x140003950  test    eax, eax
0x140003952  jnz     short loc_14000397F
0x140003954  dec     r12d
0x140003957  add     r13, 4
0x14000395b  test    r12d, r12d
0x14000395e  jg      short loc_140003934
0x140003960  lea     rcx, [rbp+0C0h+var_A0]; this
0x140003964  call    ?DecompHandler@HandlerMap4@FH4@@AEAAXXZ; FH4::HandlerMap4::DecompHandler(void)
0x140003969  mov     eax, [rsp+1C0h+var_158]
0x14000396d  inc     eax
0x14000396f  mov     [rsp+1C0h+var_158], eax
0x140003973  cmp     eax, [rsp+1C0h+var_148]
0x140003977  jnz     loc_1400038F3
0x14000397d  jmp     short loc_1400039D4
0x14000397f  mov     al, [rbp+0C0h+arg_28]
0x140003985  mov     r9, r14
0x140003988  mov     r8, [rsp+1C0h+var_150]
0x14000398d  mov     rcx, rdi; struct EHExceptionRecord *
0x140003990  mov     rdx, [rbp+0C0h+var_118]; unsigned __int64 *
0x140003994  mov     [rsp+1C0h+var_168], al; char
0x140003998  mov     al, byte ptr [rsp+1C0h+var_160]
0x14000399c  mov     byte ptr [rsp+1C0h+var_170], al; int
0x1400039a0  mov     rax, qword ptr [rbp+0C0h+var_120]
0x1400039a4  mov     qword ptr [rsp+1C0h+var_178], rax; int
0x1400039a9  mov     eax, [rbp+0C0h+arg_30]
0x1400039af  mov     [rsp+1C0h+var_180], eax; int
0x1400039b3  lea     rax, [rbp+0C0h+pExceptionObject]
0x1400039b7  mov     [rsp+1C0h+var_188], rax; __int64
0x1400039bc  lea     rax, [rbp+0C0h+var_F0]
0x1400039c0  mov     [rsp+1C0h+var_190], rbx; __int64
0x1400039c5  mov     [rsp+1C0h+var_198], rax; struct FH4::HandlerType4 *
0x1400039ca  mov     [rsp+1C0h+var_1A0], r15; struct FH4::FuncInfo4 *
0x1400039cf  call    CatchIt___FrameHandler4_
0x1400039d4  mov     r12d, [rsp+1C0h+var_15C]
0x1400039d9  mov     rbx, [rbp+0C0h+var_140]
0x1400039dd  lea     r11, cs:140000000h
0x1400039e4  mov     r10, [rbx+8]
0x1400039e8  inc     r12d
0x1400039eb  mov     rdx, r10
0x1400039ee  mov     [rsp+1C0h+var_15C], r12d
0x1400039f3  movzx   ecx, byte ptr [r10]
0x1400039f7  and     ecx, 0Fh
0x1400039fa  movsx   r9, byte ptr [rcx+r11+7460h]
0x140003a03  mov     cl, [rcx+r11+7470h]
0x140003a0b  sub     rdx, r9
0x140003a0e  mov     eax, [rdx-4]
0x140003a11  mov     [rbx+8], rdx
0x140003a15  shr     eax, cl
0x140003a17  mov     [rbx+18h], eax
0x140003a1a  movzx   ecx, byte ptr [rdx]
0x140003a1d  mov     rdx, r10
0x140003a20  and     ecx, 0Fh
0x140003a23  movsx   r8, byte ptr [rcx+r11+7460h]
0x140003a2c  mov     cl, [rcx+r11+7470h]
0x140003a34  sub     rdx, r8
0x140003a37  sub     rdx, r9
0x140003a3a  mov     eax, [rdx-4]
0x140003a3d  shr     eax, cl
0x140003a3f  mov     [rbx+1Ch], eax
0x140003a42  mov     [rbx+8], rdx
0x140003a46  movzx   ecx, byte ptr [rdx]
0x140003a49  and     ecx, 0Fh
0x140003a4c  movsx   rax, byte ptr [rcx+r11+7460h]
0x140003a55  mov     cl, [rcx+r11+7470h]
0x140003a5d  sub     r10, rax
0x140003a60  sub     r10, r8
0x140003a63  sub     r10, r9
0x140003a66  mov     eax, [r10-4]
0x140003a6a  shr     eax, cl
0x140003a6c  mov     [rbx+20h], eax
0x140003a6f  lea     rax, [r10+4]
0x140003a73  mov     [rbx+8], r10
0x140003a77  mov     ecx, [r10]
0x140003a7a  mov     [rbx+8], rax
0x140003a7e  mov     [rbx+24h], ecx
0x140003a81  cmp     r12d, [rbp+0C0h+var_F8]
0x140003a85  jb      loc_1400038A3
0x140003a8b  test    byte ptr [r15], 40h
0x140003a8f  jz      short loc_140003AE2
0x140003a91  mov     rdx, r15; struct FH4::FuncInfo4 *
0x140003a94  mov     rcx, r14; struct _xDISPATCHER_CONTEXT *
0x140003a97  call    ?ExecutionInCatch@__FrameHandler4@@SA_NPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@@Z; __FrameHandler4::ExecutionInCatch(_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *)
0x140003a9c  test    al, al
0x140003a9e  jz      loc_140003B38
0x140003aa4  jmp     short loc_140003AE2
0x140003aa6  cmp     [rbp+0C0h+var_C8], 0
0x140003aaa  jbe     short loc_140003AE2
0x140003aac  cmp     [rbp+0C0h+arg_28], 0
0x140003ab3  jnz     loc_140003B55
0x140003ab9  mov     eax, [rbp+0C0h+arg_30]
0x140003abf  mov     r9, r14
0x140003ac2  mov     [rsp+1C0h+var_188], r13; __int64
0x140003ac7  mov     r8, rbx
0x140003aca  mov     dword ptr [rsp+1C0h+var_190], eax; int
0x140003ace  mov     rdx, r12
0x140003ad1  mov     dword ptr [rsp+1C0h+var_198], esi; int
0x140003ad5  mov     rcx, rdi; struct EHExceptionRecord *
0x140003ad8  mov     [rsp+1C0h+var_1A0], r15; struct FH4::FuncInfo4 *
0x140003add  call    FindHandlerForForeignException___FrameHandler4_
0x140003ae2  call    __vcrt_getptd
0x140003ae7  cmp     qword ptr [rax+38h], 0
0x140003aec  jnz     short loc_140003B55
0x140003aee  mov     rcx, [rbp+0C0h+var_50]
0x140003af2  xor     rcx, rsp; StackCookie
0x140003af5  call    __security_check_cookie
0x140003afa  add     rsp, 188h
  ... truncated ...
```
