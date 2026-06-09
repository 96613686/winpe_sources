# _SleepStudy::IndicateClientRequestEnd_::_3_::_lambda_1_::operator()

- ea: `0x180046600`
- end: `0x180046a64`
- name: `_SleepStudy::IndicateClientRequestEnd_::_3_::_lambda_1_::operator()`
- size: `1124`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800465f0`

## callees

- `0x18003a08c`
- `0x180041044`
- `0x180046600`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046938`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046938`
- `ntdll!EtwEventWriteTransfer` at `0x180046793`
- `ntdll!EtwEventWriteTransfer` at `0x180046a28`
- `ntdll!EtwEventWriteTransfer` at `0x180046793`
- `ntdll!EtwEventWriteTransfer` at `0x180046a28`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180046930`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180046930`

## pseudocode

```c
__int64 __fastcall SleepStudy::IndicateClientRequestEnd_::_3_::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4)
{
  SleepStudy::Singleton *v5; // rax
  __int64 v6; // rcx
  _BYTE *v7; // rbx
  __int64 result; // rax
  unsigned int v9; // r11d
  _DWORD *v10; // rbx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  unsigned int *v13; // rdi
  _DWORD *v14; // r15
  unsigned __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // r14
  DWORD LastError; // esi
  unsigned int v21; // [rsp+30h] [rbp-E8h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-E4h] BYREF
  int v23; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-D8h] BYREF
  _OWORD v25[2]; // [rsp+50h] [rbp-C8h] BYREF
  int v26; // [rsp+70h] [rbp-A8h] BYREF
  int v27; // [rsp+74h] [rbp-A4h]
  __int64 v28; // [rsp+78h] [rbp-A0h]
  int *v29; // [rsp+80h] [rbp-98h] BYREF
  int v30; // [rsp+88h] [rbp-90h]
  int v31; // [rsp+8Ch] [rbp-8Ch]
  __int16 *v32; // [rsp+90h] [rbp-88h]
  int v33; // [rsp+98h] [rbp-80h]
  int v34; // [rsp+9Ch] [rbp-7Ch]
  unsigned int *v35; // [rsp+A0h] [rbp-78h]
  __int64 v36; // [rsp+A8h] [rbp-70h]
  int *v37; // [rsp+B0h] [rbp-68h]
  __int64 v38; // [rsp+B8h] [rbp-60h]
  _OWORD *v39; // [rsp+C0h] [rbp-58h]
  __int64 v40; // [rsp+C8h] [rbp-50h]
  __int64 *v41; // [rsp+D0h] [rbp-48h]
  __int64 v42; // [rsp+D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( (unsigned int)dword_18013A120 <= 4 )
  {
    v7 = (_BYTE *)(a1 + 32);
  }
  else
  {
    v5 = *(SleepStudy::Singleton **)a1;
    *(_OWORD *)((char *)v25 + 8) = 0;
    if ( *((_BYTE *)v5 + 56) )
      v6 = *((_QWORD *)v5 + 4);
    else
      v6 = 0;
    v24 = v6;
    v7 = (_BYTE *)(a1 + 32);
    if ( *(_BYTE *)(a1 + 32) )
      v25[0] = *(_OWORD *)(a1 + 16);
    else
      v25[0] = 0;
    v23 = *(_DWORD *)(a1 + 12);
    v21 = *(_DWORD *)(a1 + 8);
    v41 = &v24;
    v42 = 8;
    v39 = v25;
    v40 = 16;
    v37 = &v23;
    v38 = 4;
    v35 = &v21;
    v36 = 4;
    v26 = 184549376;
    v27 = 4;
    v28 = 0;
    v29 = off_18013A128;
    v30 = *(unsigned __int16 *)off_18013A128;
    v31 = 2;
    v32 = (__int16 *)byte_180119983;
    v33 = 118;
    v34 = 1;
    v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(RegHandle, &v26, 0, 0, 6, &v29);
  }
  try
  {
    result = *(_QWORD *)a1;
    if ( *v7 )
    {
      v9 = SleepStudy::Singleton::InterfaceIndexFromGuid(*(SleepStudy::Singleton **)a1, (const struct _GUID *)(a1 + 16));
      v10 = *(_DWORD **)(*(_QWORD *)a1 + 72LL);
      result = 0xAAAAAAAAAAAAAAABuLL;
      v11 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(*(_QWORD *)a1 + 80LL) - (_QWORD)v10) >> 4);
      while ( (__int64)v11 > 0 )
      {
        v12 = v11 >> 1;
        v13 = &v10[12 * (v11 >> 1)];
        if ( *v13 >= v9 )
        {
          if ( *v13 <= v9 )
          {
            a4 = v11 >> 1;
            if ( v12 )
            {
              do
              {
                v15 = a4 >> 1;
                if ( v10[12 * (a4 >> 1)] >= v9 )
                {
                  a4 >>= 1;
                }
                else
                {
                  v10 += 12 * (a4 >> 1) + 12;
                  result = -1LL - v15;
                  a4 += -1LL - v15;
                }
              }
              while ( (__int64)a4 > 0 );
            }
            v16 = v11 - v12 - 1;
            v14 = v13 + 12;
            while ( v16 > 0 )
            {
              v17 = v16 / 2;
              if ( v9 >= v14[12 * (v16 / 2)] )
              {
                v14 += 12 * v17 + 12;
                result = -1 - v17;
                v16 += -1 - v17;
              }
              else
              {
                v16 /= 2;
              }
            }
            goto LABEL_30;
          }
          v11 >>= 1;
        }
        else
        {
          v10 = v13 + 12;
          result = -1LL - v12;
          v11 += -1LL - v12;
        }
      }
      v14 = v10;
    }
    else
    {
      v14 = *(_DWORD **)(result + 80);
      v10 = *(_DWORD **)(result + 72);
    }
LABEL_30:
    while ( v10 != v14 )
    {
      result = *((_QWORD *)v10 + 4);
      v18 = *((_QWORD *)v10 + 3);
      if ( v18 != result )
      {
        while ( *(_DWORD *)v18 != *(_DWORD *)(a1 + 8) )
        {
          v18 += 48;
          if ( v18 == result )
          {
            v10 += 12;
            goto LABEL_30;
          }
        }
        if ( !*(_QWORD *)(v18 + 40) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        result = *(_QWORD *)(v18 + 40);
        if ( !result || (--result, (*(_QWORD *)(v18 + 40) = result) == 0) )
        {
          v19 = *(_QWORD *)(v18 + 32);
          if ( v19 )
          {
            LastError = GetLastError();
            SleepstudyHelperBlockerActiveDereference(v19);
            SetLastError(LastError);
            *(_QWORD *)(v18 + 32) = 0;
            result = (unsigned int)dword_18013A120;
            if ( (unsigned int)dword_18013A120 > 4 )
            {
              v22 = *(_DWORD *)v18;
              v37 = (int *)(v18 + 4);
              v38 = 16;
              v35 = &v22;
              v36 = 4;
              v26 = 184549376;
              v27 = 4;
              v28 = 0;
              v29 = off_18013A128;
              v30 = *(unsigned __int16 *)off_18013A128;
              v31 = 2;
              v32 = word_18011991A;
              v33 = 93;
              v34 = 1;
              v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              result = EtwEventWriteTransfer(RegHandle, &v26, 0, 0, 4, &v29);
            }
          }
        }
      }
      v10 += 12;
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x406,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
             (const char *)a4);
  }
  return result;
}

```

## disassembly

```asm
0x180046600  mov     [rsp+arg_8], rbx
0x180046605  mov     [rsp+arg_10], rsi
0x18004660a  push    rdi
0x18004660b  push    r12
0x18004660d  push    r13
0x18004660f  push    r14
0x180046611  push    r15
0x180046613  sub     rsp, 0F0h
0x18004661a  mov     rax, cs:__security_cookie
0x180046621  xor     rax, rsp
0x180046624  mov     [rsp+118h+var_38], rax
0x18004662c  mov     r12, rcx
0x18004662f  mov     eax, cs:dword_18013A120
0x180046635  cmp     eax, 4
0x180046638  jbe     loc_18004679B
0x18004663e  mov     rax, [rcx]
0x180046641  xor     r13d, r13d
0x180046644  xorps   xmm0, xmm0
0x180046647  movups  xmmword ptr [rsp+118h+var_C8+8], xmm0
0x18004664c  cmp     [rax+38h], r13b
0x180046650  jz      short loc_180046658
0x180046652  mov     rcx, [rax+20h]
0x180046656  jmp     short loc_18004665B
0x180046658  mov     rcx, r13
0x18004665b  mov     [rsp+118h+var_D8], rcx
0x180046660  lea     rbx, [r12+20h]
0x180046665  cmp     [rbx], r13b
0x180046668  jz      short loc_180046677
0x18004666a  movups  xmm0, xmmword ptr [r12+10h]
0x180046670  movaps  xmmword ptr [rsp+118h+var_C8], xmm0
0x180046675  jmp     short loc_18004667D
0x180046677  movdqa  xmmword ptr [rsp+118h+var_C8], xmm0
0x18004667d  mov     eax, [r12+0Ch]
0x180046682  mov     [rsp+118h+var_E0], eax
0x180046686  mov     eax, [r12+8]
0x18004668b  mov     [rsp+118h+var_E8], eax
0x18004668f  lea     rax, [rsp+118h+var_D8]
0x180046694  mov     [rsp+118h+var_48], rax
0x18004669c  mov     [rsp+118h+var_40], 8
0x1800466a8  lea     rax, [rsp+118h+var_C8]
0x1800466ad  mov     [rsp+118h+var_58], rax
0x1800466b5  mov     [rsp+118h+var_50], 10h
0x1800466c1  lea     rax, [rsp+118h+var_E0]
0x1800466c6  mov     [rsp+118h+var_68], rax
0x1800466ce  mov     [rsp+118h+var_60], 4
0x1800466da  lea     rax, [rsp+118h+var_E8]
0x1800466df  mov     [rsp+118h+var_78], rax
0x1800466e7  mov     [rsp+118h+var_70], 4
0x1800466f3  mov     [rsp+118h+var_A8], 0B000000h
0x1800466fb  movzx   eax, cs:word_180119979
0x180046702  mov     [rsp+118h+var_A4], eax
0x180046706  mov     [rsp+118h+var_A0], r13
0x18004670b  mov     rax, cs:off_18013A128
0x180046712  mov     [rsp+118h+var_98], rax
0x18004671a  movzx   eax, word ptr [rax]
0x18004671d  mov     [rsp+118h+var_90], eax
0x180046724  mov     [rsp+118h+var_8C], 2
0x18004672f  lea     rax, byte_180119983
0x180046736  mov     [rsp+118h+var_88], rax
0x18004673e  mov     [rsp+118h+var_80], 76h ; 'v'
0x180046749  mov     [rsp+118h+var_7C], 1
0x180046754  lea     rax, _TraceLoggingMetadataEnd
0x18004675b  lea     rdi, _TraceLoggingMetadata
0x180046762  sub     eax, edi
0x180046764  mov     [rsp+118h+var_E4], eax
0x180046768  mov     eax, [rsp+118h+var_E4]
0x18004676c  lea     rax, [rsp+118h+var_98]
0x180046774  mov     [rsp+118h+var_F0], rax
0x180046779  mov     [rsp+118h+var_F8], 6
0x180046781  xor     r9d, r9d
0x180046784  xor     r8d, r8d
0x180046787  lea     rdx, [rsp+118h+var_A8]
0x18004678c  mov     rcx, cs:RegHandle
0x180046793  call    cs:__imp_EtwEventWriteTransfer
0x180046799  jmp     short loc_1800467A2
0x18004679b  lea     rbx, [rcx+20h]
0x18004679f  xor     r13d, r13d
0x1800467a2  mov     rax, [r12]
0x1800467a6  cmp     byte ptr [rbx], 0
0x1800467a9  jz      loc_1800468B1
0x1800467af  lea     rdx, [r12+10h]; struct _GUID *
0x1800467b4  mov     rcx, rax; this
0x1800467b7  call    ?InterfaceIndexFromGuid@Singleton@SleepStudy@@AEAA@AEBU_GUID@@@Z; SleepStudy::Singleton::InterfaceIndexFromGuid(_GUID const &)
0x1800467bc  mov     r11d, eax
0x1800467bf  mov     rcx, [r12]
0x1800467c3  mov     rbx, [rcx+48h]
0x1800467c7  mov     rdx, [rcx+50h]
0x1800467cb  sub     rdx, rbx
0x1800467ce  sar     rdx, 4
0x1800467d2  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800467dc  imul    rdx, rax
0x1800467e0  test    rdx, rdx
0x1800467e3  jle     short loc_180046823
0x1800467e5  nop     word ptr [rax+rax+00000000h]
0x1800467f0  mov     rcx, rdx
0x1800467f3  shr     rcx, 1
0x1800467f6  lea     rdi, [rcx+rcx*2]
0x1800467fa  shl     rdi, 4
0x1800467fe  add     rdi, rbx
0x180046801  cmp     [rdi], r11d
0x180046804  jnb     short loc_180046819
0x180046806  lea     rbx, [rdi+30h]
0x18004680a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180046811  sub     rax, rcx
0x180046814  add     rdx, rax
0x180046817  jmp     short loc_18004681E
0x180046819  jbe     short loc_18004682B
0x18004681b  mov     rdx, rcx
0x18004681e  test    rdx, rdx
0x180046821  jg      short loc_1800467F0
0x180046823  mov     r15, rbx
0x180046826  jmp     loc_1800468C0
0x18004682b  mov     r9, rcx
0x18004682e  test    rcx, rcx
0x180046831  jz      short loc_180046865
0x180046833  mov     r8, r9
0x180046836  shr     r8, 1
0x180046839  lea     r10, [r8+r8*2]
0x18004683d  add     r10, r10
0x180046840  cmp     [rbx+r10*8], r11d
0x180046844  jnb     short loc_18004685D
0x180046846  lea     rbx, [rbx+r10*8]
0x18004684a  add     rbx, 30h ; '0'
0x18004684e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180046855  sub     rax, r8
0x180046858  add     r9, rax
0x18004685b  jmp     short loc_180046860
0x18004685d  mov     r9, r8
0x180046860  test    r9, r9
0x180046863  jg      short loc_180046833
0x180046865  sub     rdx, rcx
0x180046868  dec     rdx
0x18004686b  lea     r15, [rdi+30h]
0x18004686f  test    rdx, rdx
0x180046872  jle     short loc_1800468C0
0x180046874  mov     rcx, rdx
0x180046877  test    rdx, rdx
0x18004687a  jns     short loc_180046880
0x18004687c  lea     rcx, [rdx+1]
0x180046880  sar     rcx, 1
0x180046883  lea     r8, [rcx+rcx*2]
0x180046887  add     r8, r8
0x18004688a  cmp     r11d, [r15+r8*8]
0x18004688e  jnb     short loc_180046895
0x180046890  mov     rdx, rcx
0x180046893  jmp     short loc_1800468AA
0x180046895  lea     r15, [r15+r8*8]
0x180046899  add     r15, 30h ; '0'
0x18004689d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800468a4  sub     rax, rcx
0x1800468a7  add     rdx, rax
0x1800468aa  test    rdx, rdx
0x1800468ad  jg      short loc_180046874
0x1800468af  jmp     short loc_1800468C0
0x1800468b1  mov     r15, [rax+50h]
0x1800468b5  mov     rbx, [rax+48h]
0x1800468b9  nop     dword ptr [rax+00000000h]
0x1800468c0  cmp     rbx, r15
0x1800468c3  jz      loc_180046A37
0x1800468c9  mov     ecx, [r12+8]
0x1800468ce  mov     rax, [rbx+20h]
0x1800468d2  mov     rdi, [rbx+18h]
0x1800468d6  cmp     rdi, rax
0x1800468d9  jz      loc_180046A2E
0x1800468df  nop
0x1800468e0  cmp     [rdi], ecx
0x1800468e2  jz      short loc_1800468F3
0x1800468e4  add     rdi, 30h ; '0'
0x1800468e8  cmp     rdi, rax
0x1800468eb  jnz     short loc_1800468E0
0x1800468ed  add     rbx, 30h ; '0'
0x1800468f1  jmp     short loc_1800468C0
0x1800468f3  cmp     qword ptr [rdi+28h], 0
0x1800468f8  jnz     short loc_1800468FF
0x1800468fa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800468ff  mov     rax, [rdi+28h]
0x180046903  test    rax, rax
0x180046906  jz      short loc_180046918
0x180046908  dec     rax
0x18004690b  mov     [rdi+28h], rax
0x18004690f  test    rax, rax
0x180046912  jnz     loc_180046A2E
0x180046918  mov     r14, [rdi+20h]
0x18004691c  test    r14, r14
0x18004691f  jz      loc_180046A2E
0x180046925  call    cs:__imp_GetLastError
0x18004692b  mov     esi, eax
0x18004692d  mov     rcx, r14
0x180046930  call    cs:__imp_SleepstudyHelperBlockerActiveDereference
0x180046936  mov     ecx, esi; dwErrCode
0x180046938  call    cs:__imp_SetLastError
0x18004693e  mov     [rdi+20h], r13
0x180046942  mov     eax, cs:dword_18013A120
0x180046948  cmp     eax, 4
0x18004694b  jbe     loc_180046A2E
0x180046951  mov     eax, [rdi]
0x180046953  mov     [rsp+118h+var_E4], eax
0x180046957  add     rdi, 4
0x18004695b  mov     [rsp+118h+var_68], rdi
0x180046963  mov     [rsp+118h+var_60], 10h
0x18004696f  lea     rax, [rsp+118h+var_E4]
0x180046974  mov     [rsp+118h+var_78], rax
0x18004697c  mov     [rsp+118h+var_70], 4
0x180046988  mov     [rsp+118h+var_A8], 0B000000h
0x180046990  movzx   eax, cs:word_180119910
0x180046997  mov     [rsp+118h+var_A4], eax
0x18004699b  mov     [rsp+118h+var_A0], r13
0x1800469a0  mov     rax, cs:off_18013A128
0x1800469a7  mov     [rsp+118h+var_98], rax
0x1800469af  movzx   eax, word ptr [rax]
0x1800469b2  mov     [rsp+118h+var_90], eax
0x1800469b9  mov     [rsp+118h+var_8C], 2
0x1800469c4  lea     rax, word_18011991A
0x1800469cb  mov     [rsp+118h+var_88], rax
0x1800469d3  mov     [rsp+118h+var_80], 5Dh ; ']'
0x1800469de  mov     [rsp+118h+var_7C], 1
0x1800469e9  lea     rax, _TraceLoggingMetadataEnd
0x1800469f0  lea     rcx, _TraceLoggingMetadata
0x1800469f7  sub     eax, ecx
0x1800469f9  mov     [rsp+118h+var_E8], eax
0x1800469fd  mov     eax, [rsp+118h+var_E8]
0x180046a01  lea     rax, [rsp+118h+var_98]
0x180046a09  mov     [rsp+118h+var_F0], rax
0x180046a0e  mov     [rsp+118h+var_F8], 4
0x180046a16  xor     r9d, r9d
0x180046a19  xor     r8d, r8d
0x180046a1c  lea     rdx, [rsp+118h+var_A8]
0x180046a21  mov     rcx, cs:RegHandle
0x180046a28  call    cs:__imp_EtwEventWriteTransfer
0x180046a2e  add     rbx, 30h ; '0'
0x180046a32  jmp     loc_1800468C0
0x180046a37  mov     rcx, [rsp+118h+var_38]
0x180046a3f  xor     rcx, rsp; StackCookie
0x180046a42  call    __security_check_cookie
0x180046a47  lea     r11, [rsp+118h+var_28]
0x180046a4f  mov     rbx, [r11+38h]
0x180046a53  mov     rsi, [r11+40h]
0x180046a57  mov     rsp, r11
0x180046a5a  pop     r15
0x180046a5c  pop     r14
0x180046a5e  pop     r13
0x180046a60  pop     r12
0x180046a62  pop     rdi
0x180046a63  retn
```
