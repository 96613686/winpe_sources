# CFsrmSerializedPropDefs::Serialize(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>,CCaseInsensitiveLess<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ATL::CAdapt<CSrmRefPtr<CSerializedPropertyDefinition>>>>> const &)

- ea: `0x180087908`
- end: `0x180087ce3`
- name: `?Serialize@CFsrmSerializedPropDefs@@QEAAXAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@U?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CAdapt@V?$CSrmRefPtr@VCSerializedPropertyDefinition@@@@@ATL@@@std@@@2@@std@@@Z`
- size: `987`
- prototype: `__int64 __fastcall(CFsrmSerializedPropDefs *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18009a378`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073d04`
- `0x180086bf4`
- `0x180087908`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180087afa`
- `ole32!CoTaskMemFree` at `0x180087b60`
- `ole32!CoTaskMemFree` at `0x180087afa`
- `ole32!CoTaskMemFree` at `0x180087b60`
- `ole32!CoTaskMemAlloc` at `0x1800879d0`
- `ole32!CoTaskMemAlloc` at `0x180087a65`
- `ole32!CoTaskMemAlloc` at `0x1800879d0`
- `ole32!CoTaskMemAlloc` at `0x180087a65`

## string_xrefs

- `0x180087c65`: `CoTaskMemAlloc(FSRM_PROPERTY_DEFINITION)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CFsrmSerializedPropDefs::Serialize(CFsrmSerializedPropDefs *this, __int64 a2)
{
  __int64 v2; // rsi
  CFsrmSerializedPropDefs *v3; // r14
  unsigned int v4; // eax
  SIZE_T v5; // rbx
  void *v6; // rax
  unsigned int v7; // r12d
  __int64 *v8; // rdi
  __int64 v9; // r13
  __int64 v10; // rsi
  __int64 v11; // r15
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  SIZE_T v14; // rbx
  __int64 *v15; // rbx
  __int64 v16; // r14
  unsigned int v17; // eax
  const unsigned __int16 *v18; // rdx
  _QWORD *v19; // rdx
  __int64 *j; // rax
  __int64 *v21; // rcx
  __int64 *i; // rax
  __int64 *v23; // rcx
  char Hr; // al
  __int64 v25; // rax
  unsigned int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+28h] [rbp-D8h]
  _QWORD *v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  CFsrmSerializedPropDefs *v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  _QWORD v34[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+7Ch] [rbp-84h]
  int v37; // [rsp+80h] [rbp-80h]
  _BYTE v38[96]; // [rsp+88h] [rbp-78h] BYREF
  int v39; // [rsp+E8h] [rbp-18h]
  _BYTE v40[144]; // [rsp+F0h] [rbp-10h] BYREF
  void **v41; // [rsp+180h] [rbp+80h] BYREF
  int v42; // [rsp+188h] [rbp+88h]

  v2 = a2;
  v33 = a2;
  v3 = this;
  v32 = this;
  v30 = v34;
  v34[0] = L"base\\fs\\fsrm\\utilities\\property\\srmpropdef.cpp";
  v34[1] = L"CFsrmSerializedPropDefs::Serialize";
  v34[2] = L"PROPDEFC";
  v35 = 373;
  v36 = 17;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(v38, 0, sizeof(v38));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v41, (const struct CSrmDebugInfo *)v34, 0);
  CFsrmSerializedPropDefs::Clear(v3);
  v4 = *(_DWORD *)(v2 + 16);
  *(_DWORD *)v3 = v4;
  v5 = 32LL * v4;
  v6 = CoTaskMemAlloc(v5);
  *((_QWORD *)v3 + 1) = v6;
  if ( !v6 )
  {
    v32 = (CFsrmSerializedPropDefs *)v40;
    v25 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v40,
            (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmpropdef.cpp",
            (__int64)L"PROPDEFC",
            (__int64)L"CFsrmSerializedPropDefs::Serialize",
            383,
            17);
    CSrmFunctionTracer::Throw(&v41, v25, 2147942414LL, L"CoTaskMemAlloc(FSRM_PROPERTY_DEFINITION)");
  }
  memset_0(v6, 0, v5);
  v7 = 0;
  v8 = **(__int64 ***)(v2 + 8);
LABEL_3:
  if ( v8 != *(__int64 **)(v2 + 8) )
  {
    v9 = v8[8];
    v10 = 32LL * v7;
    v11 = *((_QWORD *)v3 + 1);
    v31 = 0;
    v12 = (const unsigned __int16 *)(v9 + 24);
    if ( *(_QWORD *)(v9 + 48) >= 8u )
      v12 = *(const unsigned __int16 **)v12;
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v31, v12);
    v13 = v31;
    v31 = 0;
    *(_QWORD *)(v10 + v11) = v13;
    *(_DWORD *)(v10 + v11 + 8) = *(_DWORD *)(v9 + 64);
    *(_DWORD *)(v10 + v11 + 24) = *(_DWORD *)(v9 + 104);
    LODWORD(v13) = *(_DWORD *)(v9 + 88);
    *(_DWORD *)(v10 + v11 + 12) = v13;
    v14 = 8LL * (unsigned int)v13;
    *(_QWORD *)(v10 + v11 + 16) = CoTaskMemAlloc(v14);
    if ( !*(_QWORD *)(v10 + v11 + 16) )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v41, -2147024882);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v41);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v41, 0x196u, Hr, 0);
    }
    v42 = 0;
    memset_0(*(void **)(v10 + v11 + 16), 0, v14);
    v15 = **(__int64 ***)(v9 + 80);
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( v15 == *(__int64 **)(v9 + 80) )
          {
            ++v7;
            CoTaskMemFree(0);
            v31 = 0;
            v2 = v33;
            v3 = v32;
            if ( *((_BYTE *)v8 + 73) )
              goto LABEL_3;
            i = (__int64 *)v8[2];
            if ( *((_BYTE *)i + 73) )
            {
              for ( i = (__int64 *)v8[1]; !*((_BYTE *)i + 73) && v8 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                v8 = i;
            }
            else
            {
              v23 = (__int64 *)*i;
              if ( !*(_BYTE *)(*i + 73) )
              {
                do
                {
                  v8 = v23;
                  v23 = (__int64 *)*v23;
                }
                while ( !*((_BYTE *)v23 + 73) );
                goto LABEL_3;
              }
            }
            v8 = i;
            goto LABEL_3;
          }
          v16 = *((unsigned int *)v15 + 16);
          v17 = *(_DWORD *)(v10 + v11 + 12);
          if ( (unsigned int)v16 >= v17 )
          {
            v26 = v17 - 1;
            v32 = (CFsrmSerializedPropDefs *)v40;
            v27 = CSrmDebugInfo::CSrmDebugInfo(
                    (__int64)v40,
                    (__int64)L"base\\fs\\fsrm\\utilities\\property\\srmpropdef.cpp",
                    (__int64)L"PROPDEFC",
                    (__int64)L"CFsrmSerializedPropDefs::Serialize",
                    418,
                    17);
            LODWORD(v29) = v26;
            LODWORD(v28) = v16;
            CSrmFunctionTracer::Throw(
              &v41,
              v27,
              2147549183LL,
              L"Index of possible value (%d) is out of range (max = %d)",
              v28,
              v29);
          }
          v30 = 0;
          v18 = (const unsigned __int16 *)(v15 + 3);
          if ( (unsigned __int64)v15[6] >= 8 )
            v18 = *(const unsigned __int16 **)v18;
          CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v30, v18);
          v19 = v30;
          v30 = 0;
          *(_QWORD *)(*(_QWORD *)(v10 + v11 + 16) + 8 * v16) = v19;
          CoTaskMemFree(0);
          v30 = 0;
        }
        while ( *((_BYTE *)v15 + 73) );
        j = (__int64 *)v15[2];
        if ( !*((_BYTE *)j + 73) )
          break;
        for ( j = (__int64 *)v15[1]; !*((_BYTE *)j + 73) && v15 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v15 = j;
LABEL_21:
        v15 = j;
      }
      v21 = (__int64 *)*j;
      if ( *(_BYTE *)(*j + 73) )
        goto LABEL_21;
      do
      {
        v15 = v21;
        v21 = (__int64 *)*v21;
      }
      while ( !*((_BYTE *)v21 + 73) );
    }
  }
  v41 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v41);
}

```

## disassembly

```asm
0x180087908  push    rbp
0x18008790a  push    rbx
0x18008790b  push    rsi
0x18008790c  push    rdi
0x18008790d  push    r12
0x18008790f  push    r13
0x180087911  push    r14
0x180087913  push    r15
0x180087915  lea     rbp, [rsp-148h]
0x18008791d  sub     rsp, 248h
0x180087924  mov     rax, cs:__security_cookie
0x18008792b  xor     rax, rsp
0x18008792e  mov     [rbp+180h+var_50], rax
0x180087935  mov     rsi, rdx
0x180087938  mov     [rsp+280h+var_228], rdx
0x18008793d  mov     r14, rcx
0x180087940  mov     [rsp+280h+var_230], rcx
0x180087945  lea     rax, [rsp+280h+var_220]
0x18008794a  mov     [rsp+280h+var_240], rax
0x18008794f  lea     rdi, aBaseFsFsrmUtil_20
0x180087956  mov     [rsp+280h+var_220], rdi
0x18008795b  lea     r15, aCfsrmserialize
0x180087962  mov     [rsp+280h+var_218], r15
0x180087967  lea     r12, aPropdefc
0x18008796e  mov     [rsp+280h+var_210], r12
0x180087973  mov     [rsp+280h+var_208], 175h
0x18008797b  mov     r13d, 11h
0x180087981  mov     [rsp+280h+var_204], r13d
0x180087986  mov     [rbp+180h+var_200], 0FFh
0x18008798d  mov     [rbp+180h+var_198], 1000000h
0x180087994  xor     edx, edx; Val
0x180087996  lea     r8d, [r13+4Fh]; Size
0x18008799a  lea     rcx, [rbp+180h+var_1F8]; void *
0x18008799e  call    memset_0
0x1800879a3  nop
0x1800879a4  xor     r8d, r8d
0x1800879a7  lea     rdx, [rsp+280h+var_220]
0x1800879ac  lea     rcx, [rbp+180h+var_100]
0x1800879b3  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z
0x1800879b8  nop
0x1800879b9  mov     rcx, r14; this
0x1800879bc  call    ?Clear@CFsrmSerializedPropDefs@@QEAAXXZ
0x1800879c1  mov     eax, [rsi+10h]
0x1800879c4  mov     [r14], eax
0x1800879c7  mov     ebx, eax
0x1800879c9  shl     rbx, 5
0x1800879cd  mov     rcx, rbx; cb
0x1800879d0  call    cs:__imp_CoTaskMemAlloc
0x1800879d6  mov     [r14+8], rax
0x1800879da  test    rax, rax
0x1800879dd  jz      loc_180087C3C
0x1800879e3  mov     r8, rbx; Size
0x1800879e6  xor     edx, edx; Val
0x1800879e8  mov     rcx, rax; void *
0x1800879eb  call    memset_0
0x1800879f0  xor     r12d, r12d
0x1800879f3  mov     rdi, [rsi+8]
0x1800879f7  mov     rdi, [rdi]
0x1800879fa  cmp     rdi, [rsi+8]
0x1800879fe  jz      loc_180087BCA
0x180087a04  mov     r13, [rdi+40h]
0x180087a08  mov     esi, r12d
0x180087a0b  shl     rsi, 5
0x180087a0f  mov     r15, [r14+8]
0x180087a13  xor     r14d, r14d
0x180087a16  mov     [rsp+280h+var_238], r14
0x180087a1b  lea     rdx, [r13+18h]
0x180087a1f  cmp     qword ptr [rdx+18h], 8
0x180087a24  jb      short loc_180087A29
0x180087a26  mov     rdx, [rdx]; unsigned __int16 *
0x180087a29  lea     rcx, [rsp+280h+var_238]; this
0x180087a2e  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z
0x180087a33  mov     rax, [rsp+280h+var_238]
0x180087a38  mov     [rsp+280h+var_238], r14
0x180087a3d  mov     [rsi+r15], rax
0x180087a41  mov     eax, [r13+40h]
0x180087a45  mov     [rsi+r15+8], eax
0x180087a4a  mov     eax, [r13+68h]
0x180087a4e  mov     [rsi+r15+18h], eax
0x180087a53  mov     eax, [r13+58h]
0x180087a57  mov     [rsi+r15+0Ch], eax
0x180087a5c  mov     ebx, eax
0x180087a5e  shl     rbx, 3
0x180087a62  mov     rcx, rbx; cb
0x180087a65  call    cs:__imp_CoTaskMemAlloc
0x180087a6b  mov     [rsi+r15+10h], rax
0x180087a70  mov     eax, [rbp+180h+var_F8]
0x180087a76  mov     [rbp+180h+var_F8], eax
0x180087a7c  cmp     [rsi+r15+10h], r14
0x180087a81  jz      loc_180087C07
0x180087a87  mov     [rbp+180h+var_F8], r14d
0x180087a8e  mov     r8, rbx; Size
0x180087a91  xor     edx, edx; Val
0x180087a93  mov     rcx, [rsi+r15+10h]; void *
0x180087a98  call    memset_0
0x180087a9d  mov     rbx, [r13+50h]
0x180087aa1  mov     rbx, [rbx]
0x180087aa4  cmp     rbx, [r13+50h]
0x180087aa8  jz      loc_180087B5B
0x180087aae  mov     r14d, [rbx+40h]
0x180087ab2  mov     eax, [rsi+r15+0Ch]
0x180087ab7  cmp     r14d, eax
0x180087aba  jnb     loc_180087C82
0x180087ac0  mov     [rsp+280h+var_240], 0
0x180087ac9  lea     rdx, [rbx+18h]
0x180087acd  cmp     qword ptr [rdx+18h], 8
0x180087ad2  jb      short loc_180087AD7
0x180087ad4  mov     rdx, [rdx]; unsigned __int16 *
0x180087ad7  lea     rcx, [rsp+280h+var_240]; this
0x180087adc  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z
0x180087ae1  mov     rdx, [rsp+280h+var_240]
0x180087ae6  mov     [rsp+280h+var_240], 0
0x180087aef  mov     rax, [rsi+r15+10h]
0x180087af4  mov     [rax+r14*8], rdx
0x180087af8  xor     ecx, ecx; pv
0x180087afa  call    cs:__imp_CoTaskMemFree
0x180087b00  xor     r14d, r14d
0x180087b03  mov     [rsp+280h+var_240], r14
0x180087b08  mov     [rsp+280h+var_240], r14
0x180087b0d  cmp     [rbx+49h], r14b
0x180087b11  jnz     short loc_180087AA4
0x180087b13  mov     rax, [rbx+10h]
0x180087b17  cmp     [rax+49h], r14b
0x180087b1b  jnz     short loc_180087B3A
0x180087b1d  mov     rcx, [rax]
0x180087b20  cmp     [rcx+49h], r14b
0x180087b24  jnz     short loc_180087B53
0x180087b26  mov     rbx, rcx
0x180087b29  mov     rax, [rcx]
0x180087b2c  mov     rcx, rax
0x180087b2f  cmp     [rax+49h], r14b
0x180087b33  jz      short loc_180087B26
0x180087b35  jmp     loc_180087AA4
0x180087b3a  mov     rax, [rbx+8]
0x180087b3e  jmp     short loc_180087B4D
0x180087b40  cmp     rbx, [rax+10h]
0x180087b44  jnz     short loc_180087B53
0x180087b46  mov     rbx, rax
0x180087b49  mov     rax, [rax+8]
0x180087b4d  cmp     [rax+49h], r14b
0x180087b51  jz      short loc_180087B40
0x180087b53  mov     rbx, rax
0x180087b56  jmp     loc_180087AA4
0x180087b5b  inc     r12d
0x180087b5e  xor     ecx, ecx; pv
0x180087b60  call    cs:__imp_CoTaskMemFree
0x180087b66  mov     [rsp+280h+var_238], r14
0x180087b6b  mov     [rsp+280h+var_238], r14
0x180087b70  cmp     [rdi+49h], r14b
0x180087b74  mov     rsi, [rsp+280h+var_228]
0x180087b79  mov     r14, [rsp+280h+var_230]
0x180087b7e  jnz     loc_1800879FA
0x180087b84  mov     rax, [rdi+10h]
0x180087b88  xor     edx, edx
0x180087b8a  cmp     [rax+49h], dl
0x180087b8d  jnz     short loc_180087BAA
0x180087b8f  mov     rcx, [rax]
0x180087b92  cmp     [rcx+49h], dl
0x180087b95  jnz     short loc_180087BC2
0x180087b97  mov     rdi, rcx
0x180087b9a  mov     rax, [rcx]
0x180087b9d  mov     rcx, rax
0x180087ba0  cmp     [rax+49h], dl
0x180087ba3  jz      short loc_180087B97
0x180087ba5  jmp     loc_1800879FA
0x180087baa  mov     rax, [rdi+8]
0x180087bae  jmp     short loc_180087BBD
0x180087bb0  cmp     rdi, [rax+10h]
0x180087bb4  jnz     short loc_180087BC2
0x180087bb6  mov     rdi, rax
0x180087bb9  mov     rax, [rax+8]
0x180087bbd  cmp     [rax+49h], dl
0x180087bc0  jz      short loc_180087BB0
0x180087bc2  mov     rdi, rax
0x180087bc5  jmp     loc_1800879FA
0x180087bca  lea     rax, ??_7CSrmFunctionTracer@@6B@
0x180087bd1  mov     [rbp+180h+var_100], rax
0x180087bd8  lea     rcx, [rbp+180h+var_100]; this
0x180087bdf  call    ??1CSrmFunctionTracerBase@@UEAA@XZ
0x180087be4  mov     rcx, [rbp+180h+var_50]
0x180087beb  xor     rcx, rsp; StackCookie
0x180087bee  call    __security_check_cookie
0x180087bf3  add     rsp, 248h
0x180087bfa  pop     r15
0x180087bfc  pop     r14
0x180087bfe  pop     r13
0x180087c00  pop     r12
0x180087c02  pop     rdi
0x180087c03  pop     rsi
0x180087c04  pop     rbx
0x180087c05  pop     rbp
0x180087c06  retn
0x180087c07  mov     edx, 8007000Eh; int
0x180087c0c  lea     rcx, [rbp+180h+var_100]; this
0x180087c13  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z
0x180087c18  lea     rcx, [rbp+180h+var_100]; this
0x180087c1f  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ
0x180087c24  mov     r8d, eax; char
0x180087c27  xor     r9d, r9d; unsigned __int16 *
0x180087c2a  mov     edx, 196h; unsigned int
0x180087c2f  lea     rcx, [rbp+180h+var_100]; this
0x180087c36  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ
0x180087c3c  lea     rax, [rbp+180h+var_190]
0x180087c40  mov     [rsp+280h+var_230], rax
0x180087c45  mov     dword ptr [rsp+280h+var_258], r13d
0x180087c4a  mov     dword ptr [rsp+280h+var_260], 17Fh
0x180087c52  mov     r9, r15
0x180087c55  mov     r8, r12
0x180087c58  mov     rdx, rdi
0x180087c5b  lea     rcx, [rbp+180h+var_190]
0x180087c5f  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z
0x180087c64  nop
0x180087c65  lea     r9, aCotaskmemalloc_2
0x180087c6c  mov     r8d, 8007000Eh
0x180087c72  mov     rdx, rax
0x180087c75  lea     rcx, [rbp+180h+var_100]
0x180087c7c  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ
0x180087c82  lea     ebx, [rax-1]
0x180087c85  lea     rax, [rbp+180h+var_190]
0x180087c89  mov     [rsp+280h+var_230], rax
0x180087c8e  mov     dword ptr [rsp+280h+var_258], 11h
0x180087c96  mov     dword ptr [rsp+280h+var_260], 1A2h
0x180087c9e  lea     r9, aCfsrmserialize
0x180087ca5  lea     r8, aPropdefc
0x180087cac  lea     rdx, aBaseFsFsrmUtil_20
0x180087cb3  lea     rcx, [rbp+180h+var_190]
0x180087cb7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z
0x180087cbc  nop
0x180087cbd  mov     dword ptr [rsp+280h+var_258], ebx
0x180087cc1  mov     dword ptr [rsp+280h+var_260], r14d
0x180087cc6  lea     r9, aIndexOfPossibl
0x180087ccd  mov     r8d, 8000FFFFh
0x180087cd3  mov     rdx, rax
0x180087cd6  lea     rcx, [rbp+180h+var_100]
0x180087cdd  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ
```
