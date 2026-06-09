# CreateOrExtendCorrelationVector(char const *)

- ea: `0x18001fb14`
- end: `0x18001fd56`
- name: `?CreateOrExtendCorrelationVector@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z`
- size: `578`
- prototype: `__int64 __fastcall(void *, char *)`
- caller_count: `5`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180015bd0`
- `0x18001ef70`
- `0x18001f588`
- `0x18001f790`
- `0x18001f914`

## callees

- `0x1800140f0`
- `0x18001840c`
- `0x180019d80`
- `0x18001fb14`
- `0x18001fd5c`
- `0x180021160`
- `0x18002b1b0`
- `0x18002bc68`
- `0x18002bd28`
- `0x18002e495`
- `0x180033d5c`
- `0x180042f48`
- `0x18004d1ec`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001fcca`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001fcca`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001fb8e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001fb8e`

## pseudocode

```c
_QWORD *__fastcall CreateOrExtendCorrelationVector(_QWORD *a1, char *a2)
{
  volatile signed __int64 *v3; // rbx
  unsigned int v4; // edx
  HRESULT v5; // eax
  __int64 v6; // rbx
  size_t v7; // r14
  __int64 v8; // rbx
  _BYTE *v9; // rax
  _BYTE *v10; // rdi
  int v12; // [rsp+20h] [rbp-E0h]
  GUID v13; // [rsp+30h] [rbp-D0h] BYREF
  GUID pguid; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Source[22]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v16; // [rsp+66h] [rbp-9Ah]
  __int16 v17; // [rsp+D1h] [rbp-2Fh]
  signed __int64 v18; // [rsp+D8h] [rbp-28h] BYREF
  char Destination[144]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *(_QWORD *)&pguid.Data1 = a1;
  if ( a2 )
  {
    v3 = (volatile signed __int64 *)TraceLoggingCorrelationVector::Extend(a2, (bool)a2);
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v3,
      _InterlockedExchangeAdd64(v3 + 17, 0),
      Destination);
    if ( v3 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v3, v4);
  }
  else
  {
    pguid = 0;
    v5 = CoCreateGuid(&pguid);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecoreuap\\shell\\twinui\\pickercore\\api\\lib\\winrtpicker.cpp",
        (const char *)(unsigned int)v5,
        v12);
    v17 = -32489;
    v13 = pguid;
    v18 = 0x1900000000LL;
    memset_0(Source, 0, 0x81u);
    TLV::Base64Encode<129>(&v13, 16, Source);
    v16 = 46;
    v6 = _InterlockedExchangeAdd64(&v18, 0);
    Destination[0] = 0;
    if ( !memcpy_s_0(Destination, HIBYTE(v17), Source, WORD2(v6)) )
    {
      if ( v6 >= 0 )
      {
        sprintf_s(&Destination[(unsigned __int8)v17], HIBYTE(v17) - (unsigned __int64)(unsigned __int8)v17, "%u", v6);
      }
      else if ( (_DWORD)v6 )
      {
        sprintf_s(&Destination[(unsigned __int8)v17], HIBYTE(v17) - (unsigned __int64)(unsigned __int8)v17, "%u!", v6);
      }
      else
      {
        Destination[(unsigned __int8)v17] = 33;
        Destination[(unsigned __int8)v17 + 1] = 0;
      }
    }
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  v7 = -1;
  a1[3] = 0;
  do
    ++v7;
  while ( Destination[v7] );
  if ( v7 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("string too long");
  if ( v7 > 0xF )
  {
    v8 = std::string::_Calculate_growth(v7);
    v9 = (_BYTE *)std::_Allocate<16,std::_Default_allocate_traits>(v8 + 1);
    *a1 = v9;
    a1[2] = v7;
    a1[3] = v8;
    v10 = v9;
    memcpy_0(v9, Destination, v7);
    v10[v7] = 0;
  }
  else
  {
    a1[3] = 15;
    a1[2] = v7;
    memcpy_0(a1, Destination, v7);
    *((_BYTE *)a1 + v7) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001fb14  mov     [rsp-8+arg_10], rbx
0x18001fb19  mov     [rsp-8+arg_18], rsi
0x18001fb1e  push    rbp
0x18001fb1f  push    rdi
0x18001fb20  push    r14
0x18001fb22  lea     rbp, [rsp-80h]
0x18001fb27  sub     rsp, 180h
0x18001fb2e  mov     rax, cs:__security_cookie
0x18001fb35  xor     rax, rsp
0x18001fb38  mov     [rbp+90h+var_20], rax
0x18001fb3c  mov     qword ptr [rsp+190h+pguid.Data1], rcx
0x18001fb41  mov     rsi, rcx
0x18001fb44  test    rdx, rdx
0x18001fb47  jz      short loc_18001FB81
0x18001fb49  mov     rcx, rdx; char *
0x18001fb4c  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x18001fb51  mov     rbx, rax
0x18001fb54  xor     edx, edx
0x18001fb56  lock xadd [rax+88h], rdx; unsigned __int64
0x18001fb5f  lea     r8, [rbp+90h+Destination]; char *
0x18001fb63  mov     rcx, rax; this
0x18001fb66  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001fb6b  test    rbx, rbx
0x18001fb6e  jz      loc_18001FC8C
0x18001fb74  mov     rcx, rbx; this
0x18001fb77  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x18001fb7c  jmp     loc_18001FC8C
0x18001fb81  xorps   xmm0, xmm0
0x18001fb84  lea     rcx, [rsp+190h+pguid]; pguid
0x18001fb89  movups  xmmword ptr [rsp+190h+pguid.Data1], xmm0
0x18001fb8e  call    cs:__imp_CoCreateGuid
0x18001fb94  test    eax, eax
0x18001fb96  jns     short loc_18001FBB4
0x18001fb98  mov     rcx, [rbp+98h]; this
0x18001fb9f  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\twinui\\pickercore\\"...
0x18001fba6  mov     r9d, eax; char *
0x18001fba9  mov     edx, 0C0h; void *
0x18001fbae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001fbb4  movaps  xmm0, xmmword ptr [rsp+190h+pguid.Data1]
0x18001fbb9  lea     rcx, [rsp+190h+Source]; void *
0x18001fbbe  mov     rax, 1900000000h
0x18001fbc8  mov     [rbp+90h+var_BF], 8117h
0x18001fbce  xor     edx, edx; Val
0x18001fbd0  movdqa  [rsp+190h+var_160], xmm0
0x18001fbd6  mov     r8d, 81h; Size
0x18001fbdc  mov     [rbp+90h+var_B8], rax
0x18001fbe0  call    memset_0
0x18001fbe5  lea     r8, [rsp+190h+Source]
0x18001fbea  mov     edx, 10h
0x18001fbef  lea     rcx, [rsp+190h+var_160]
0x18001fbf4  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18001fbf9  xor     ebx, ebx
0x18001fbfb  mov     [rsp+190h+var_12A], 2Eh ; '.'
0x18001fc02  lock xadd [rbp+90h+var_B8], rbx
0x18001fc08  movzx   edx, byte ptr [rbp+90h+var_BF+1]; DestinationSize
0x18001fc0c  lea     r8, [rsp+190h+Source]; Source
0x18001fc11  test    rbx, rbx
0x18001fc14  mov     [rbp+90h+Destination], 0
0x18001fc18  mov     rax, rbx
0x18001fc1b  lea     rcx, [rbp+90h+Destination]; Destination
0x18001fc1f  sets    dil
0x18001fc23  shr     rax, 20h
0x18001fc27  movzx   r9d, ax; SourceSize
0x18001fc2b  call    memcpy_s_0
0x18001fc30  test    eax, eax
0x18001fc32  jnz     short loc_18001FC8C
0x18001fc34  movzx   eax, byte ptr [rbp+90h+var_BF]
0x18001fc38  test    dil, dil
0x18001fc3b  jz      short loc_18001FC6F
0x18001fc3d  test    ebx, ebx
0x18001fc3f  jnz     short loc_18001FC50
0x18001fc41  mov     [rbp+rax+90h+Destination], 21h ; '!'
0x18001fc46  movzx   eax, byte ptr [rbp+90h+var_BF]
0x18001fc4a  mov     [rbp+rax+90h+var_AF], bl
0x18001fc4e  jmp     short loc_18001FC8C
0x18001fc50  movzx   edx, byte ptr [rbp+90h+var_BF+1]
0x18001fc54  lea     rcx, [rbp+90h+Destination]
0x18001fc58  sub     rdx, rax; BufferCount
0x18001fc5b  lea     r8, Format; "%u!"
0x18001fc62  add     rcx, rax; Buffer
0x18001fc65  mov     r9d, ebx
0x18001fc68  call    sprintf_s
0x18001fc6d  jmp     short loc_18001FC8C
0x18001fc6f  movzx   edx, byte ptr [rbp+90h+var_BF+1]
0x18001fc73  lea     rcx, [rbp+90h+Destination]
0x18001fc77  sub     rdx, rax; BufferCount
0x18001fc7a  lea     r8, aU_0; "%u"
0x18001fc81  add     rcx, rax; Buffer
0x18001fc84  mov     r9d, ebx
0x18001fc87  call    sprintf_s
0x18001fc8c  xorps   xmm0, xmm0
0x18001fc8f  lea     rax, [rbp+90h+Destination]
0x18001fc93  movups  xmmword ptr [rsi], xmm0
0x18001fc96  mov     qword ptr [rsi+10h], 0
0x18001fc9e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001fca2  mov     qword ptr [rsi+18h], 0
0x18001fcaa  inc     r14
0x18001fcad  cmp     byte ptr [rax+r14], 0
0x18001fcb2  jnz     short loc_18001FCAA
0x18001fcb4  mov     r8, 7FFFFFFFFFFFFFFFh
0x18001fcbe  cmp     r14, r8
0x18001fcc1  jbe     short loc_18001FCD1
0x18001fcc3  lea     rcx, aStringTooLong; "string too long"
0x18001fcca  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001fcd1  mov     edx, 0Fh
0x18001fcd6  cmp     r14, rdx
0x18001fcd9  ja      short loc_18001FCF9
0x18001fcdb  mov     [rsi+18h], rdx
0x18001fcdf  mov     r8, r14; Size
0x18001fce2  lea     rdx, [rbp+90h+Destination]; Src
0x18001fce6  mov     [rsi+10h], r14
0x18001fcea  mov     rcx, rsi; void *
0x18001fced  call    memcpy_0
0x18001fcf2  mov     byte ptr [r14+rsi], 0
0x18001fcf7  jmp     short loc_18001FD2F
0x18001fcf9  mov     rcx, r14
0x18001fcfc  call    ?_Calculate_growth@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CA_K_K00@Z; std::string::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001fd01  mov     rbx, rax
0x18001fd04  lea     rcx, [rax+1]
0x18001fd08  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001fd0d  mov     r8, r14; Size
0x18001fd10  mov     [rsi], rax
0x18001fd13  lea     rdx, [rbp+90h+Destination]; Src
0x18001fd17  mov     [rsi+10h], r14
0x18001fd1b  mov     rcx, rax; void *
0x18001fd1e  mov     [rsi+18h], rbx
0x18001fd22  mov     rdi, rax
0x18001fd25  call    memcpy_0
0x18001fd2a  mov     byte ptr [r14+rdi], 0
0x18001fd2f  mov     rax, rsi
0x18001fd32  mov     rcx, [rbp+90h+var_20]
0x18001fd36  xor     rcx, rsp; StackCookie
0x18001fd39  call    __security_check_cookie
0x18001fd3e  lea     r11, [rsp+190h+var_10]
0x18001fd46  mov     rbx, [r11+30h]
0x18001fd4a  mov     rsi, [r11+38h]
0x18001fd4e  mov     rsp, r11
0x18001fd51  pop     r14
0x18001fd53  pop     rdi
0x18001fd54  pop     rbp
0x18001fd55  retn
```
