# LogSyncRootLastAccessTime(ushort const *,ushort const *,ushort const *,CF_HYDRATION_POLICY,CF_POPULATION_POLICY,std::map<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>> *,ulong,long)

- ea: `0x18001a93c`
- end: `0x18001abe3`
- name: `?LogSyncRootLastAccessTime@@YAXPEBG00UCF_HYDRATION_POLICY@@UCF_POPULATION_POLICY@@PEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@KJ@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800180a0`

## callees

- `0x1800010b0`
- `0x180001650`
- `0x180017dc8`
- `0x18001a93c`

## pseudocode

```c
__int64 __fastcall LogSyncRootLastAccessTime(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        int a8)
{
  __int64 result; // rax
  __int64 v13; // rcx
  int v14; // r8d
  int v15; // r9d
  int v16; // [rsp+C0h] [rbp-80h] BYREF
  int v17; // [rsp+C4h] [rbp-7Ch] BYREF
  int v18; // [rsp+C8h] [rbp-78h] BYREF
  int v19; // [rsp+CCh] [rbp-74h] BYREF
  int v20; // [rsp+D0h] [rbp-70h] BYREF
  int v21; // [rsp+D4h] [rbp-6Ch] BYREF
  int v22; // [rsp+D8h] [rbp-68h] BYREF
  int v23; // [rsp+DCh] [rbp-64h] BYREF
  int v24; // [rsp+E0h] [rbp-60h] BYREF
  int v25; // [rsp+E4h] [rbp-5Ch] BYREF
  int v26; // [rsp+E8h] [rbp-58h] BYREF
  int v27; // [rsp+ECh] [rbp-54h] BYREF
  int v28; // [rsp+F0h] [rbp-50h] BYREF
  int v29; // [rsp+F4h] [rbp-4Ch] BYREF
  int v30; // [rsp+F8h] [rbp-48h] BYREF
  int v31; // [rsp+FCh] [rbp-44h] BYREF
  __int64 v32; // [rsp+100h] [rbp-40h] BYREF
  __int64 v33; // [rsp+108h] [rbp-38h] BYREF
  __int64 v34; // [rsp+110h] [rbp-30h] BYREF
  __int64 v35; // [rsp+118h] [rbp-28h] BYREF
  __int64 v36; // [rsp+120h] [rbp-20h] BYREF
  __int64 v37; // [rsp+128h] [rbp-18h] BYREF
  __int64 v38; // [rsp+130h] [rbp-10h] BYREF
  __int64 v39; // [rsp+138h] [rbp-8h] BYREF
  __int64 v40; // [rsp+140h] [rbp+0h] BYREF
  __int64 v41; // [rsp+148h] [rbp+8h] BYREF
  __int64 v42; // [rsp+150h] [rbp+10h] BYREF
  __int64 v43; // [rsp+158h] [rbp+18h] BYREF
  __int64 v44; // [rsp+160h] [rbp+20h] BYREF
  __int64 v45; // [rsp+168h] [rbp+28h] BYREF
  __int64 v46; // [rsp+170h] [rbp+30h] BYREF
  _QWORD v47[7]; // [rsp+178h] [rbp+38h] BYREF

  result = (unsigned int)dword_180040010;
  if ( (unsigned int)dword_180040010 > 5 )
  {
    result = tlgKeywordOn(&dword_180040010, 0x400000000000LL, a3);
    if ( (_BYTE)result )
    {
      v32 = 0x1000000;
      v28 = a8;
      v16 = 34;
      v33 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v16);
      v17 = 33;
      v34 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v17);
      v18 = 32;
      v35 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v18);
      v19 = 31;
      v36 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v19);
      v20 = 30;
      v37 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v20);
      v21 = 29;
      v38 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v21);
      v22 = 28;
      v39 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v22);
      v23 = 27;
      v40 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v23);
      v24 = 26;
      v41 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v24);
      v25 = 25;
      v42 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v25);
      v26 = 24;
      v43 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v26);
      v27 = 23;
      v13 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a6, &v27);
      v29 = a7;
      v30 = a5;
      v44 = v13;
      v31 = a4;
      v45 = a3;
      v46 = a2;
      v47[0] = a1;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
               v13,
               (unsigned int)word_1800382CA,
               v14,
               v15,
               (__int64)v47,
               (__int64)&v46,
               (__int64)&v45,
               (__int64)&v31,
               (__int64)&v30,
               (__int64)&v29,
               (__int64)&v44,
               (__int64)&v43,
               (__int64)&v42,
               (__int64)&v41,
               (__int64)&v40,
               (__int64)&v39,
               (__int64)&v38,
               (__int64)&v37,
               (__int64)&v36,
               (__int64)&v35,
               (__int64)&v34,
               (__int64)&v33,
               (__int64)&v28,
               (__int64)&v32);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a93c  push    rbp
0x18001a93e  push    rbx
0x18001a93f  push    rsi
0x18001a940  push    rdi
0x18001a941  push    r14
0x18001a943  push    r15
0x18001a945  lea     rbp, [rsp-48h]
0x18001a94a  sub     rsp, 188h
0x18001a951  mov     eax, cs:dword_180040010
0x18001a957  mov     ebx, r9d
0x18001a95a  mov     rsi, r8
0x18001a95d  mov     r14, rdx
0x18001a960  mov     r15, rcx
0x18001a963  cmp     eax, 5
0x18001a966  jbe     loc_18001ABD3
0x18001a96c  mov     rdx, 400000000000h
0x18001a976  lea     rcx, dword_180040010
0x18001a97d  call    _tlgKeywordOn
0x18001a982  test    al, al
0x18001a984  jz      loc_18001ABD3
0x18001a98a  mov     eax, [rbp+70h+arg_38]
0x18001a990  lea     rdx, [rbp+70h+var_F0]
0x18001a994  mov     rdi, [rbp+70h+arg_28]
0x18001a99b  mov     rcx, rdi
0x18001a99e  mov     [rbp+70h+var_B0], 1000000h
0x18001a9a6  mov     [rbp+70h+var_C0], eax
0x18001a9a9  mov     [rbp+70h+var_F0], 22h ; '"'
0x18001a9b0  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001a9b5  lea     rdx, [rbp+70h+var_EC]
0x18001a9b9  mov     rcx, [rax]
0x18001a9bc  mov     [rbp+70h+var_A8], rcx
0x18001a9c0  mov     rcx, rdi
0x18001a9c3  mov     [rbp+70h+var_EC], 21h ; '!'
0x18001a9ca  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001a9cf  lea     rdx, [rbp+70h+var_E8]
0x18001a9d3  mov     rcx, [rax]
0x18001a9d6  mov     [rbp+70h+var_A0], rcx
0x18001a9da  mov     rcx, rdi
0x18001a9dd  mov     [rbp+70h+var_E8], 20h ; ' '
0x18001a9e4  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001a9e9  lea     rdx, [rbp+70h+var_E4]
0x18001a9ed  mov     rcx, [rax]
0x18001a9f0  mov     [rbp+70h+var_98], rcx
0x18001a9f4  mov     rcx, rdi
0x18001a9f7  mov     [rbp+70h+var_E4], 1Fh
0x18001a9fe  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aa03  lea     rdx, [rbp+70h+var_E0]
0x18001aa07  mov     rcx, [rax]
0x18001aa0a  mov     [rbp+70h+var_90], rcx
0x18001aa0e  mov     rcx, rdi
0x18001aa11  mov     [rbp+70h+var_E0], 1Eh
0x18001aa18  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aa1d  lea     rdx, [rbp+70h+var_DC]
0x18001aa21  mov     rcx, [rax]
0x18001aa24  mov     [rbp+70h+var_88], rcx
0x18001aa28  mov     rcx, rdi
0x18001aa2b  mov     [rbp+70h+var_DC], 1Dh
0x18001aa32  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aa37  lea     rdx, [rbp+70h+var_D8]
0x18001aa3b  mov     rcx, [rax]
0x18001aa3e  mov     [rbp+70h+var_80], rcx
0x18001aa42  mov     rcx, rdi
0x18001aa45  mov     [rbp+70h+var_D8], 1Ch
0x18001aa4c  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aa51  lea     rdx, [rbp+70h+var_D4]
0x18001aa55  mov     rcx, [rax]
0x18001aa58  mov     [rbp+70h+var_78], rcx
0x18001aa5c  mov     rcx, rdi
0x18001aa5f  mov     [rbp+70h+var_D4], 1Bh
0x18001aa66  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aa6b  lea     rdx, [rbp+70h+var_D0]
0x18001aa6f  mov     rcx, [rax]
0x18001aa72  mov     [rbp+70h+var_70], rcx
0x18001aa76  mov     rcx, rdi
0x18001aa79  mov     [rbp+70h+var_D0], 1Ah
0x18001aa80  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aa85  lea     rdx, [rbp+70h+var_CC]
0x18001aa89  mov     rcx, [rax]
0x18001aa8c  mov     [rbp+70h+var_68], rcx
0x18001aa90  mov     rcx, rdi
0x18001aa93  mov     [rbp+70h+var_CC], 19h
0x18001aa9a  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aa9f  mov     rcx, rdi
0x18001aaa2  mov     rdx, [rax]
0x18001aaa5  mov     [rbp+70h+var_60], rdx
0x18001aaa9  lea     rdx, [rbp+70h+var_C8]
0x18001aaad  mov     [rbp+70h+var_C8], 18h
0x18001aab4  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aab9  mov     rcx, rdi
0x18001aabc  mov     rdx, [rax]
0x18001aabf  mov     [rbp+70h+var_58], rdx
0x18001aac3  lea     rdx, [rbp+70h+var_C4]
0x18001aac7  mov     [rbp+70h+var_C4], 17h
0x18001aace  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001aad3  mov     rcx, [rax]
0x18001aad6  mov     eax, [rbp+70h+arg_30]
0x18001aadc  mov     [rbp+70h+var_BC], eax
0x18001aadf  mov     eax, [rbp+70h+arg_20]
0x18001aae5  mov     [rbp+70h+var_B8], eax
0x18001aae8  mov     [rbp+70h+var_50], rcx
0x18001aaec  mov     [rbp+70h+var_B4], ebx
0x18001aaef  lea     rax, [rbp+70h+var_B0]
0x18001aaf3  mov     [rbp+70h+var_48], rsi
0x18001aaf7  mov     [rsp+1B0h+var_F8], rax
0x18001aaff  lea     rdx, word_1800382CA
0x18001ab06  lea     rax, [rbp+70h+var_C0]
0x18001ab0a  mov     [rbp+70h+var_40], r14
0x18001ab0e  mov     [rsp+1B0h+var_100], rax
0x18001ab16  lea     rax, [rbp+70h+var_A8]
0x18001ab1a  mov     [rsp+1B0h+var_108], rax
0x18001ab22  lea     rax, [rbp+70h+var_A0]
0x18001ab26  mov     [rsp+1B0h+var_110], rax
0x18001ab2e  lea     rax, [rbp+70h+var_98]
0x18001ab32  mov     [rsp+1B0h+var_118], rax
0x18001ab3a  lea     rax, [rbp+70h+var_90]
0x18001ab3e  mov     [rsp+1B0h+var_120], rax
0x18001ab46  lea     rax, [rbp+70h+var_88]
0x18001ab4a  mov     [rsp+1B0h+var_128], rax
0x18001ab52  lea     rax, [rbp+70h+var_80]
0x18001ab56  mov     [rsp+1B0h+var_130], rax
0x18001ab5e  lea     rax, [rbp+70h+var_78]
0x18001ab62  mov     [rsp+1B0h+var_138], rax
0x18001ab67  lea     rax, [rbp+70h+var_70]
0x18001ab6b  mov     [rsp+1B0h+var_140], rax
0x18001ab70  lea     rax, [rbp+70h+var_68]
0x18001ab74  mov     [rsp+1B0h+var_148], rax
0x18001ab79  lea     rax, [rbp+70h+var_60]
0x18001ab7d  mov     [rsp+1B0h+var_150], rax
0x18001ab82  lea     rax, [rbp+70h+var_58]
0x18001ab86  mov     [rsp+1B0h+var_158], rax
0x18001ab8b  lea     rax, [rbp+70h+var_50]
0x18001ab8f  mov     [rsp+1B0h+var_160], rax
0x18001ab94  lea     rax, [rbp+70h+var_BC]
0x18001ab98  mov     [rsp+1B0h+var_168], rax
0x18001ab9d  lea     rax, [rbp+70h+var_B8]
0x18001aba1  mov     [rsp+1B0h+var_170], rax
0x18001aba6  lea     rax, [rbp+70h+var_B4]
0x18001abaa  mov     [rsp+1B0h+var_178], rax
0x18001abaf  lea     rax, [rbp+70h+var_48]
0x18001abb3  mov     [rsp+1B0h+var_180], rax
0x18001abb8  lea     rax, [rbp+70h+var_40]
0x18001abbc  mov     [rsp+1B0h+var_188], rax
0x18001abc1  lea     rax, [rbp+70h+var_38]
0x18001abc5  mov     [rsp+1B0h+var_190], rax
0x18001abca  mov     [rbp+70h+var_38], r15
0x18001abce  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByVal@$07@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByVal@$07@@5555555555545@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001abd3  add     rsp, 188h
0x18001abda  pop     r15
0x18001abdc  pop     r14
0x18001abde  pop     rdi
0x18001abdf  pop     rsi
0x18001abe0  pop     rbx
0x18001abe1  pop     rbp
0x18001abe2  retn
```
