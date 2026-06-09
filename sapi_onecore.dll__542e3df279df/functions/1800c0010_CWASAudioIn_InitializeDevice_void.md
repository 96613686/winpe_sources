# CWASAudioIn::InitializeDevice(void)

- ea: `0x1800c0010`
- end: `0x1800c0882`
- name: `?InitializeDevice@CWASAudioIn@@AEAAJXZ`
- size: `2162`
- prototype: `__int64 __fastcall(CWASAudioIn *__hidden this)`
- caller_count: `5`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bee20`
- `0x1800c18d0`
- `0x1800c1a20`
- `0x1800c1ab0`
- `0x1800c1df0`

## callees

- `0x18000bec4`
- `0x180013ec0`
- `0x1800458e4`
- `0x18007aa24`
- `0x18007d31c`
- `0x18008b5b8`
- `0x1800aa860`
- `0x1800be764`
- `0x1800bea2c`
- `0x1800bf484`
- `0x1800c0010`
- `0x1800c0a84`
- `0x1800c0aac`
- `0x1800cd45c`
- `0x1800cd71c`
- `0x1800cd8b8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c0050`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c0050`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c085d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c085d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c02ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c03dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0852`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c02ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c03dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0852`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c040f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c040f`

## string_xrefs

- `0x1800c05ae`: `[%s] Write AudioProcessingPolicy telemetry`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWASAudioIn::InitializeDevice(CWASAudioIn *this)
{
  unsigned int v2; // r13d
  signed int AudioClientProperties; // r15d
  CWASAudioIn *v4; // rcx
  struct AudioClientProperties *v5; // rbx
  __int64 v6; // rcx
  int *v7; // rax
  unsigned __int16 v8; // dx
  int v9; // r9d
  float v10; // xmm6_4
  float v11; // xmm0_4
  int v12; // r9d
  double v13; // xmm1_8
  int v14; // esi
  __int64 v15; // rdx
  int i; // edi
  unsigned __int16 *v17; // r12
  __int64 v18; // rcx
  const wchar_t *v19; // r9
  char v20; // al
  unsigned int v21; // esi
  unsigned int v22; // r9d
  unsigned int v23; // r10d
  unsigned int v24; // r11d
  BOOL v25; // edi
  int v26; // r8d
  unsigned int v27; // eax
  unsigned int v28; // ecx
  unsigned __int16 *v29; // rdx
  unsigned __int64 v30; // rdx
  unsigned __int8 Data1; // cl
  TimestampLogger *v32; // rax
  __int64 v33; // rdx
  TimestampLogger *v34; // rax
  TimestampLogger *v35; // rcx
  int v36; // eax
  int v38; // [rsp+38h] [rbp-E0h]
  unsigned int v39; // [rsp+78h] [rbp-A0h]
  LPVOID pv; // [rsp+98h] [rbp-80h] BYREF
  int v41; // [rsp+A0h] [rbp-78h] BYREF
  struct _GUID v42; // [rsp+A8h] [rbp-70h] BYREF
  struct AudioClientProperties *v43; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-58h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+C8h] [rbp-50h]
  struct _GUID v46; // [rsp+D8h] [rbp-40h] BYREF
  unsigned __int64 v47; // [rsp+E8h] [rbp-30h]
  int v48; // [rsp+158h] [rbp+40h] BYREF
  unsigned int v49; // [rsp+160h] [rbp+48h] BYREF
  TimestampLogger *v50; // [rsp+168h] [rbp+50h] BYREF
  int v51; // [rsp+170h] [rbp+58h] BYREF

  v47 = ((unsigned __int64)this + 88) & -(__int64)(this != 0);
  lpCriticalSection = (LPCRITICAL_SECTION)(v47 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v47 + 8));
  DoTraceMessage(16, "[%s] start", "CWASAudioIn::InitializeDevice");
  v2 = 0;
  if ( CWASAudioIn::IsDeviceInitialized(this) )
  {
    AudioClientProperties = -2147024891;
  }
  else
  {
    AudioClientProperties = 0;
    if ( !*((_DWORD *)this + 100156)
      || !*((_DWORD *)this + 88)
      || (AudioClientProperties = CSpStreamFormat::AssignChannelCount((CWASAudioIn *)((char *)this + 328), 1u),
          AudioClientProperties >= 0) )
    {
      if ( !CWASAudioIn::IsDeviceActivated(this) )
        AudioClientProperties = CWASAudioIn::ActivateDevice(v4);
    }
  }
  v5 = 0;
  v43 = 0;
  if ( AudioClientProperties >= 0 )
  {
    AudioClientProperties = CWASAudioIn::GetAudioClientProperties(this, &v43);
    v5 = v43;
    if ( AudioClientProperties >= 0 )
      AudioClientProperties = (*(__int64 (__fastcall **)(_QWORD, struct AudioClientProperties *))(**((_QWORD **)this + 57)
                                                                                                + 128LL))(
                                *((_QWORD *)this + 57),
                                v43);
  }
  pv = 0;
  if ( AudioClientProperties >= 0 )
    AudioClientProperties = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 57) + 64LL))(
                              *((_QWORD *)this + 57),
                              &pv);
  v6 = 0;
  v44 = 0;
  if ( AudioClientProperties >= 0 )
  {
    AudioClientProperties = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 57))(
                              *((_QWORD *)this + 57),
                              &GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb,
                              &v44);
    v6 = v44;
  }
  v41 = 0;
  v48 = 0;
  v51 = 0;
  v49 = 0;
  if ( AudioClientProperties >= 0 )
  {
    AudioClientProperties = (*(__int64 (__fastcall **)(__int64, LPVOID, int *, int *, int *, unsigned int *))(*(_QWORD *)v6 + 24LL))(
                              v6,
                              pv,
                              &v41,
                              &v48,
                              &v51,
                              &v49);
    DoTraceMessage(
      8,
      "[%s] m_cpAudioClient->GetExtendedSharedModeEnginePeriod() returned hr = 0x%x - %i, %i, %i, %i",
      "CWASAudioIn::InitializeDevice",
      AudioClientProperties,
      v41,
      v48,
      v51,
      v49);
    if ( AudioClientProperties >= 0 )
    {
      v7 = (int *)pv;
      v8 = *((_WORD *)pv + 1);
      *((_WORD *)this + 200314) = v8;
      if ( *((_DWORD *)this + 88) )
      {
        AudioClientProperties = CSpStreamFormat::AssignChannelCount((CWASAudioIn *)((char *)this + 328), v8);
        if ( AudioClientProperties < 0 )
          goto LABEL_50;
        v7 = (int *)pv;
      }
      v9 = *((_DWORD *)this + 149);
      v10 = (float)((float)v9 / 1000.0) * (float)v7[1];
      DoTraceMessage(8, "[%s] Max samples supported - %d", "CWASAudioIn::InitializeDevice", v9);
      v11 = floorf(v10 / (float)v48);
      v12 = v48 * (int)v11;
      if ( v49 < v12 )
        v12 = v49;
      v13 = (double)v12 * 10000.0 * 1000.0 / (double)*((int *)pv + 1) + 0.5;
      v14 = (int)v13;
      DoTraceMessage(
        8,
        "[%s] Using engine period %d with hns period %d\n",
        "CWASAudioIn::InitializeDevice",
        v12,
        (int)v13);
      v15 = *((_QWORD *)this + 43);
      if ( *((_DWORD *)this + 100156) )
      {
        if ( *(_WORD *)(v15 + 14) == 16 )
        {
          if ( *((_WORD *)this + 200314) <= 2u )
          {
            *(_WORD *)pv = 1;
            *((_WORD *)pv + 8) = 0;
          }
          else
          {
            v42 = 0;
            CoTaskMemFree(pv);
            pv = 0;
            *((_WORD *)this + 200314) = *(_WORD *)(*((_QWORD *)this + 43) + 2LL);
            AudioClientProperties = CSpStreamFormat::CopyTo(
                                      (CWASAudioIn *)((char *)this + 328),
                                      &v42,
                                      (struct tWAVEFORMATEX **)&pv);
          }
        }
        *((_DWORD *)pv + 1) = *(_DWORD *)(*((_QWORD *)this + 43) + 4LL);
        *((_WORD *)pv + 6) = *((unsigned __int16 *)pv + 6)
                           / (int)(*((unsigned __int16 *)pv + 7)
                                 / (unsigned int)*(unsigned __int16 *)(*((_QWORD *)this + 43) + 14LL));
        *((_WORD *)pv + 7) = *(_WORD *)(*((_QWORD *)this + 43) + 14LL);
        *((_DWORD *)pv + 2) = *((_DWORD *)pv + 1) * *((unsigned __int16 *)pv + 6);
      }
      else
      {
        if ( *(_WORD *)v15 == 3
          && *((_WORD *)pv + 7) == *(_WORD *)(v15 + 14)
          && *(_WORD *)(v15 + 2) == *((_WORD *)pv + 1) )
        {
          *((_DWORD *)pv + 1) = *(_DWORD *)(v15 + 4);
          *((_DWORD *)pv + 2) = *(_DWORD *)(*((_QWORD *)this + 43) + 8LL);
          goto LABEL_34;
        }
        v42 = 0;
        CoTaskMemFree(pv);
        pv = 0;
        AudioClientProperties = CSpStreamFormat::CopyTo(
                                  (CWASAudioIn *)((char *)this + 328),
                                  &v42,
                                  (struct tWAVEFORMATEX **)&pv);
      }
      if ( AudioClientProperties < 0 )
      {
LABEL_41:
        if ( *((_QWORD *)this + 50102) )
        {
          if ( AudioClientProperties >= 0 )
            AudioClientProperties = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 57) + 104LL))(
                                      *((_QWORD *)this + 57),
                                      *((_QWORD *)this + 50102));
          LODWORD(v50) = 0;
          if ( AudioClientProperties >= 0 )
          {
            AudioClientProperties = (*(__int64 (__fastcall **)(_QWORD, TimestampLogger **))(**((_QWORD **)this + 57)
                                                                                          + 32LL))(
                                      *((_QWORD *)this + 57),
                                      &v50);
            if ( AudioClientProperties >= 0 )
            {
              *((_DWORD *)this + 147) = (_DWORD)v50 * *((unsigned __int16 *)pv + 6);
              if ( *((_DWORD *)this + 80)
                || (AudioClientProperties = (*(__int64 (__fastcall **)(CWASAudioIn *, __int64 *))(*(_QWORD *)this + 144LL))(
                                              this,
                                              qword_1802BBC00),
                    AudioClientProperties >= 0) )
              {
                *((_DWORD *)this + 100150) = 0;
              }
            }
          }
        }
        else
        {
          DoTraceMessage(
            8,
            "[%s] InitializeDevice, invalid m_autohCaptureEvent handle",
            "CWASAudioIn::InitializeDevice");
          AudioClientProperties = -2147200979;
          LODWORD(v50) = 0;
        }
        goto LABEL_50;
      }
LABEL_34:
      for ( i = 0; i <= 3; ++i )
      {
        if ( i )
        {
          Sleep(0xFu);
          DoTraceMessage(8, "[%s] AudioClient Retrying... (%d).", "CWASAudioIn::InitializeDevice", i);
        }
        DoTraceMessage(16, "[%s] cpAudioClientInternal->Initialize()", "CWASAudioIn::InitializeDevice");
        AudioClientProperties = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID, _QWORD))(*(_QWORD *)v44 + 32LL))(
                                  v44,
                                  2147745792LL,
                                  (unsigned int)(int)v13,
                                  pv,
                                  0);
        DoTraceMessage(
          8,
          "[%s] cpAudioClientInternal->Initialize() returned hr = 0x%x",
          "CWASAudioIn::InitializeDevice",
          AudioClientProperties);
        if ( AudioClientProperties != -2004287465 )
          break;
      }
      v5 = v43;
      if ( AudioClientProperties >= 0 )
      {
        *((_DWORD *)this + 148) = v14 / 10000;
        DoTraceMessage(8, "[%s] buffer duration %d ms", "CWASAudioIn::InitializeDevice", v14 / 10000);
      }
      goto LABEL_41;
    }
  }
LABEL_50:
  if ( !*((_BYTE *)this + 400748) || *((_DWORD *)this + 100156) )
  {
    if ( AudioClientProperties < 0 )
      goto LABEL_82;
  }
  else
  {
    DoTraceMessage(8, "[%s] Write AudioProcessingPolicy telemetry", "CWASAudioIn::InitializeDevice");
    v17 = 0;
    *(_QWORD *)&v42.Data1 = 0;
    v18 = *((_QWORD *)this + 72);
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v18 + 40LL))(v18, &v42);
      v19 = L"NULL";
      if ( *(_QWORD *)&v42.Data1 )
        v19 = *(const wchar_t **)&v42.Data1;
      DoTraceMessage(8, "[%s] Capture Endpoint ID %S", "CWASAudioIn::InitializeDevice", v19);
      v17 = *(unsigned __int16 **)&v42.Data1;
    }
    if ( *((_QWORD *)this + 72) )
    {
      v20 = 1;
      LODWORD(v50) = 0;
    }
    else
    {
      v20 = 0;
      v2 = -1;
      LODWORD(v50) = -1;
    }
    v21 = -(v20 == 0);
    v22 = *((_DWORD *)this + 100192);
    v23 = *((_DWORD *)this + 100191);
    v24 = *((_DWORD *)this + 100190);
    v25 = *((_BYTE *)this + 400749) != 0;
    v26 = *((_DWORD *)this + 124) & 1;
    v27 = *((unsigned __int16 *)this + 200314);
    v28 = *((_DWORD *)this + 100188);
    v29 = L"Empty";
    if ( v17 )
      v29 = v17;
    v46 = *(struct _GUID *)((char *)this + 400772);
    SPTelemetry::AudioProcessingPolicy(
      &v46,
      v29,
      AudioClientProperties,
      *((_DWORD *)this + 100189),
      v28,
      v27,
      v38,
      v26,
      v25,
      v24,
      v23,
      v22,
      v21,
      v2,
      v39,
      (unsigned int)v50,
      *((_DWORD *)this + 124));
    Data1 = v42.Data1;
    if ( *(_QWORD *)&v42.Data1 )
    {
      CoTaskMemFree(*(LPVOID *)&v42.Data1);
      *(_QWORD *)&v42.Data1 = 0;
    }
    if ( AudioClientProperties < 0 )
      goto LABEL_82;
    if ( !*((_QWORD *)this + 50099) && SPTelemetry::IsEnabled(Data1, v30) )
    {
      v32 = (TimestampLogger *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
      v50 = v32;
      if ( v32 )
        v34 = TimestampLogger::TimestampLogger(v32);
      else
        v34 = 0;
      *((_QWORD *)this + 50099) = v34;
      if ( !v34 )
      {
        AudioClientProperties = -2147024882;
        goto LABEL_82;
      }
      AudioClientProperties = TimestampLogger::Initialize(v34, v33, *((_QWORD *)this + 50082));
      if ( AudioClientProperties < 0 )
        goto LABEL_82;
    }
    v35 = (TimestampLogger *)*((_QWORD *)this + 50099);
    if ( v35 )
    {
      v46 = *(struct _GUID *)((char *)this + 400772);
      TimestampLogger::OnStreamInitialize(v35, &v46, *(_DWORD *)(*((_QWORD *)this + 43) + 4LL));
    }
  }
  if ( *((_DWORD *)this + 140) != -1 )
  {
    AudioClientProperties = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *))(**((_QWORD **)this + 59) + 56LL))(
                              *((_QWORD *)this + 59),
                              **((_QWORD **)this + 59),
                              &GUID_00000000_0000_0000_0000_000000000000);
    if ( AudioClientProperties < 0 )
      goto LABEL_82;
    *((_DWORD *)this + 140) = -1;
  }
  v36 = (*(__int64 (__fastcall **)(_QWORD, GUID *, char *))(**((_QWORD **)this + 57) + 112LL))(
          *((_QWORD *)this + 57),
          &IID_IAudioCaptureClient,
          (char *)this + 464);
  AudioClientProperties = v36;
  if ( v36 >= 0 )
    *((_BYTE *)this + 400748) = 0;
  else
    DoTraceMessage(8, "[%s] Can't get IAudioCaptureClient pointer! (0x%x).", "CWASAudioIn::InitializeDevice", v36);
LABEL_82:
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v44);
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v5);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)AudioClientProperties;
}

```

## disassembly

```asm
0x1800c0010  mov     rax, rsp
0x1800c0013  push    rbp
0x1800c0014  push    rbx
0x1800c0015  push    rsi
0x1800c0016  push    rdi
0x1800c0017  push    r12
0x1800c0019  push    r13
0x1800c001b  push    r14
0x1800c001d  push    r15
0x1800c001f  lea     rbp, [rax-38h]
0x1800c0023  sub     rsp, 108h
0x1800c002a  movaps  xmmword ptr [rax-58h], xmm6
0x1800c002e  mov     r14, rcx
0x1800c0031  mov     rax, rcx
0x1800c0034  lea     rdx, [rcx+58h]
0x1800c0038  neg     rax
0x1800c003b  sbb     r8, r8
0x1800c003e  and     r8, rdx
0x1800c0041  mov     [rbp+30h+var_60], r8
0x1800c0045  lea     rax, [r8+8]
0x1800c0049  mov     [rbp+30h+lpCriticalSection], rax
0x1800c004d  mov     rcx, rax; lpCriticalSection
0x1800c0050  call    cs:__imp_EnterCriticalSection
0x1800c0056  nop
0x1800c0057  lea     r12, aCwasaudioinIni; "CWASAudioIn::InitializeDevice"
0x1800c005e  mov     r8, r12
0x1800c0061  lea     rdx, aSStart; "[%s] start"
0x1800c0068  mov     ecx, 10h; int
0x1800c006d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c0072  mov     rcx, r14; this
0x1800c0075  call    ?IsDeviceInitialized@CWASAudioIn@@AEAA_NXZ; CWASAudioIn::IsDeviceInitialized(void)
0x1800c007a  mov     esi, 1
0x1800c007f  xor     r13d, r13d
0x1800c0082  test    al, al
0x1800c0084  jz      short loc_1800C008E
0x1800c0086  mov     r15d, 80070005h
0x1800c008c  jmp     short loc_1800C00C9
0x1800c008e  mov     r15d, r13d
0x1800c0091  cmp     [r14+61CF0h], r13d
0x1800c0098  jz      short loc_1800C00B5
0x1800c009a  lea     rcx, [r14+148h]; this
0x1800c00a1  cmp     [rcx+18h], r13d
0x1800c00a5  jz      short loc_1800C00B5
0x1800c00a7  mov     edx, esi; unsigned __int16
0x1800c00a9  call    ?AssignChannelCount@CSpStreamFormat@@QEAAJG@Z; CSpStreamFormat::AssignChannelCount(ushort)
0x1800c00ae  mov     r15d, eax
0x1800c00b1  test    eax, eax
0x1800c00b3  js      short loc_1800C00C9
0x1800c00b5  mov     rcx, r14; this
0x1800c00b8  call    ?IsDeviceActivated@CWASAudioIn@@AEAA_NXZ; CWASAudioIn::IsDeviceActivated(void)
0x1800c00bd  test    al, al
0x1800c00bf  jnz     short loc_1800C00C9
0x1800c00c1  call    ?ActivateDevice@CWASAudioIn@@AEAAJXZ; CWASAudioIn::ActivateDevice(void)
0x1800c00c6  mov     r15d, eax
0x1800c00c9  mov     rbx, r13
0x1800c00cc  mov     [rbp+30h+var_90], rbx
0x1800c00d0  test    r15d, r15d
0x1800c00d3  js      short loc_1800C0108
0x1800c00d5  lea     rdx, [rbp+30h+var_90]; struct AudioClientProperties **
0x1800c00d9  mov     rcx, r14; this
0x1800c00dc  call    ?GetAudioClientProperties@CWASAudioIn@@AEAAJPEAPEAUAudioClientProperties@@@Z; CWASAudioIn::GetAudioClientProperties(AudioClientProperties * *)
0x1800c00e1  mov     r15d, eax
0x1800c00e4  mov     rbx, [rbp+30h+var_90]
0x1800c00e8  test    eax, eax
0x1800c00ea  js      short loc_1800C0108
0x1800c00ec  mov     rcx, [r14+1C8h]
0x1800c00f3  mov     rax, [rcx]
0x1800c00f6  mov     rdx, rbx
0x1800c00f9  mov     rax, [rax+80h]
0x1800c0100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0105  mov     r15d, eax
0x1800c0108  mov     [rbp+30h+pv], r13
0x1800c010c  test    r15d, r15d
0x1800c010f  js      short loc_1800C012B
0x1800c0111  mov     rcx, [r14+1C8h]
0x1800c0118  mov     rax, [rcx]
0x1800c011b  lea     rdx, [rbp+30h+pv]
0x1800c011f  mov     rax, [rax+40h]
0x1800c0123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0128  mov     r15d, eax
0x1800c012b  mov     rcx, r13
0x1800c012e  mov     [rbp+30h+var_88], rcx
0x1800c0132  test    r15d, r15d
0x1800c0135  js      short loc_1800C015B
0x1800c0137  mov     rcx, [r14+1C8h]
0x1800c013e  mov     rax, [rcx]
0x1800c0141  lea     r8, [rbp+30h+var_88]
0x1800c0145  lea     rdx, _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb
0x1800c014c  mov     rax, [rax]
0x1800c014f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0154  mov     r15d, eax
0x1800c0157  mov     rcx, [rbp+30h+var_88]
0x1800c015b  mov     [rbp+30h+var_A8], r13d
0x1800c015f  mov     [rbp+30h+arg_0], r13d
0x1800c0163  mov     [rbp+30h+arg_18], r13d
0x1800c0167  mov     [rbp+30h+arg_8], r13d
0x1800c016b  test    r15d, r15d
0x1800c016e  js      loc_1800C058E
0x1800c0174  mov     rax, [rcx]
0x1800c0177  lea     rdx, [rbp+30h+arg_8]
0x1800c017b  mov     qword ptr [rsp+140h+var_118], rdx
0x1800c0180  lea     rdx, [rbp+30h+arg_18]
0x1800c0184  mov     qword ptr [rsp+140h+var_120], rdx
0x1800c0189  lea     r9, [rbp+30h+arg_0]
0x1800c018d  lea     r8, [rbp+30h+var_A8]
0x1800c0191  mov     rdx, [rbp+30h+pv]
0x1800c0195  mov     rax, [rax+18h]
0x1800c0199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c019e  mov     r15d, eax
0x1800c01a1  mov     eax, [rbp+30h+arg_8]
0x1800c01a4  mov     [rsp+140h+var_108], eax
0x1800c01a8  mov     eax, [rbp+30h+arg_18]
0x1800c01ab  mov     [rsp+140h+var_110], eax; int
0x1800c01af  mov     eax, [rbp+30h+arg_0]
0x1800c01b2  mov     [rsp+140h+var_118], eax
0x1800c01b6  mov     eax, [rbp+30h+var_A8]
0x1800c01b9  mov     [rsp+140h+var_120], eax
0x1800c01bd  mov     r9d, r15d
0x1800c01c0  mov     r8, r12
0x1800c01c3  lea     rdx, aSMCpaudioclien; "[%s] m_cpAudioClient->GetExtendedShared"...
0x1800c01ca  mov     ecx, 8; int
0x1800c01cf  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c01d4  test    r15d, r15d
0x1800c01d7  js      loc_1800C058E
0x1800c01dd  mov     rax, [rbp+30h+pv]
0x1800c01e1  movzx   edx, word ptr [rax+2]; unsigned __int16
0x1800c01e5  mov     [r14+61CF4h], dx
0x1800c01ed  lea     rdi, [r14+148h]
0x1800c01f4  cmp     [rdi+18h], r13d
0x1800c01f8  jz      short loc_1800C0211
0x1800c01fa  mov     rcx, rdi; this
0x1800c01fd  call    ?AssignChannelCount@CSpStreamFormat@@QEAAJG@Z; CSpStreamFormat::AssignChannelCount(ushort)
0x1800c0202  mov     r15d, eax
0x1800c0205  test    eax, eax
0x1800c0207  js      loc_1800C058E
0x1800c020d  mov     rax, [rbp+30h+pv]
0x1800c0211  mov     r9d, [r14+254h]
0x1800c0218  xorps   xmm6, xmm6
0x1800c021b  cvtsi2ss xmm6, r9
0x1800c0220  divss   xmm6, cs:__real@447a0000
0x1800c0228  mov     ecx, [rax+4]
0x1800c022b  xorps   xmm1, xmm1
0x1800c022e  cvtsi2ss xmm1, rcx
0x1800c0233  mulss   xmm6, xmm1
0x1800c0237  mov     r8, r12
0x1800c023a  lea     rdx, aSMaxSamplesSup; "[%s] Max samples supported - %d"
0x1800c0241  mov     ecx, 8; int
0x1800c0246  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c024b  mov     eax, [rbp+30h+arg_0]
0x1800c024e  xorps   xmm1, xmm1
0x1800c0251  cvtsi2ss xmm1, rax
0x1800c0256  divss   xmm6, xmm1
0x1800c025a  movaps  xmm0, xmm6; X
0x1800c025d  call    floorf
0x1800c0262  cvttss2si r9, xmm0
0x1800c0267  imul    r9d, [rbp+30h+arg_0]
0x1800c026c  cmp     [rbp+30h+arg_8], r9d
0x1800c0270  cmovb   r9d, [rbp+30h+arg_8]
0x1800c0275  mov     eax, r9d
0x1800c0278  xorps   xmm1, xmm1
0x1800c027b  cvtsi2sd xmm1, rax
0x1800c0280  mulsd   xmm1, cs:__real@40c3880000000000
0x1800c0288  mulsd   xmm1, cs:__real@408f400000000000
0x1800c0290  mov     rax, [rbp+30h+pv]
0x1800c0294  mov     ecx, [rax+4]
0x1800c0297  xorps   xmm0, xmm0
0x1800c029a  cvtsi2sd xmm0, rcx
0x1800c029f  divsd   xmm1, xmm0
0x1800c02a3  addsd   xmm1, cs:__real@3fe0000000000000
0x1800c02ab  cvttsd2si rsi, xmm1
0x1800c02b0  mov     [rsp+140h+var_120], esi
0x1800c02b4  mov     r8, r12
0x1800c02b7  lea     rdx, aSUsingEnginePe; "[%s] Using engine period %d with hns pe"...
0x1800c02be  mov     ecx, 8; int
0x1800c02c3  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c02c8  mov     rdx, [rdi+10h]
0x1800c02cc  mov     eax, 3
0x1800c02d1  cmp     [r14+61CF0h], r13d
0x1800c02d8  jz      loc_1800C03A0
0x1800c02de  mov     eax, 10h
0x1800c02e3  cmp     [rdx+0Eh], ax
0x1800c02e7  jnz     short loc_1800C0343
0x1800c02e9  cmp     word ptr [r14+61CF4h], 2
0x1800c02f2  jbe     short loc_1800C0331
0x1800c02f4  xorps   xmm0, xmm0
0x1800c02f7  movups  xmmword ptr [rbp+30h+var_A0.Data1], xmm0
0x1800c02fb  mov     rcx, [rbp+30h+pv]; pv
0x1800c02ff  call    cs:__imp_CoTaskMemFree
0x1800c0305  mov     [rbp+30h+pv], r13
0x1800c0309  mov     rax, [r14+158h]
0x1800c0310  movzx   edx, word ptr [rax+2]
0x1800c0314  mov     [r14+61CF4h], dx
0x1800c031c  lea     r8, [rbp+30h+pv]; struct tWAVEFORMATEX **
0x1800c0320  lea     rdx, [rbp+30h+var_A0]; struct _GUID *
0x1800c0324  mov     rcx, rdi; this
0x1800c0327  call    ?CopyTo@CSpStreamFormat@@QEBAJPEAU_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; CSpStreamFormat::CopyTo(_GUID *,tWAVEFORMATEX * *)
0x1800c032c  mov     r15d, eax
0x1800c032f  jmp     short loc_1800C0343
0x1800c0331  mov     rax, [rbp+30h+pv]
0x1800c0335  mov     word ptr [rax], 1
0x1800c033a  mov     rax, [rbp+30h+pv]
0x1800c033e  mov     [rax+10h], r13w
0x1800c0343  mov     rax, [r14+158h]
0x1800c034a  mov     ecx, [rax+4]
0x1800c034d  mov     rax, [rbp+30h+pv]
0x1800c0351  mov     [rax+4], ecx
0x1800c0354  mov     rcx, [rbp+30h+pv]
0x1800c0358  movzx   eax, word ptr [rcx+0Eh]
0x1800c035c  mov     rdx, [r14+158h]
0x1800c0363  movzx   r8d, word ptr [rdx+0Eh]
0x1800c0368  xor     edx, edx
0x1800c036a  div     r8d
0x1800c036d  mov     r8d, eax
0x1800c0370  movzx   eax, word ptr [rcx+0Ch]
0x1800c0374  cdq
0x1800c0375  idiv    r8d
0x1800c0378  mov     [rcx+0Ch], ax
0x1800c037c  mov     rax, [r14+158h]
0x1800c0383  movzx   ecx, word ptr [rax+0Eh]
0x1800c0387  mov     rax, [rbp+30h+pv]
0x1800c038b  mov     [rax+0Eh], cx
0x1800c038f  mov     rax, [rbp+30h+pv]
0x1800c0393  movzx   ecx, word ptr [rax+0Ch]
0x1800c0397  imul    ecx, [rax+4]
0x1800c039b  mov     [rax+8], ecx
0x1800c039e  jmp     short loc_1800C03FA
0x1800c03a0  mov     rcx, [rbp+30h+pv]; pv
0x1800c03a4  cmp     [rdx], ax
0x1800c03a7  jnz     short loc_1800C03D6
0x1800c03a9  movzx   eax, word ptr [rdx+0Eh]
0x1800c03ad  cmp     [rcx+0Eh], ax
0x1800c03b1  jnz     short loc_1800C03D6
0x1800c03b3  movzx   eax, word ptr [rcx+2]
0x1800c03b7  cmp     [rdx+2], ax
0x1800c03bb  jnz     short loc_1800C03D6
0x1800c03bd  mov     eax, [rdx+4]
0x1800c03c0  mov     [rcx+4], eax
0x1800c03c3  mov     rax, [r14+158h]
0x1800c03ca  mov     ecx, [rax+8]
0x1800c03cd  mov     rax, [rbp+30h+pv]
0x1800c03d1  mov     [rax+8], ecx
0x1800c03d4  jmp     short loc_1800C0403
0x1800c03d6  xorps   xmm0, xmm0
0x1800c03d9  movups  xmmword ptr [rbp+30h+var_A0.Data1], xmm0
0x1800c03dd  call    cs:__imp_CoTaskMemFree
0x1800c03e3  mov     [rbp+30h+pv], r13
0x1800c03e7  lea     r8, [rbp+30h+pv]; struct tWAVEFORMATEX **
0x1800c03eb  lea     rdx, [rbp+30h+var_A0]; struct _GUID *
0x1800c03ef  mov     rcx, rdi; this
0x1800c03f2  call    ?CopyTo@CSpStreamFormat@@QEBAJPEAU_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; CSpStreamFormat::CopyTo(_GUID *,tWAVEFORMATEX * *)
0x1800c03f7  mov     r15d, eax
0x1800c03fa  test    r15d, r15d
0x1800c03fd  js      loc_1800C04D1
0x1800c0403  mov     edi, r13d
0x1800c0406  test    edi, edi
0x1800c0408  jz      short loc_1800C042C
0x1800c040a  mov     ecx, 0Fh; dwMilliseconds
0x1800c040f  call    cs:__imp_Sleep
0x1800c0415  mov     r9d, edi
0x1800c0418  mov     r8, r12
0x1800c041b  lea     rdx, aSAudioclientRe; "[%s] AudioClient Retrying... (%d)."
0x1800c0422  mov     ecx, 8; int
0x1800c0427  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c042c  mov     r8, r12
0x1800c042f  lea     rdx, aSCpaudioclient_0; "[%s] cpAudioClientInternal->Initialize("...
0x1800c0436  mov     ecx, 10h; int
0x1800c043b  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c0440  mov     rcx, [rbp+30h+var_88]
0x1800c0444  mov     rax, [rcx]
0x1800c0447  mov     qword ptr [rsp+140h+var_120], r13
0x1800c044c  mov     r9, [rbp+30h+pv]
0x1800c0450  mov     r8, rsi
0x1800c0453  mov     edx, 80040000h
0x1800c0458  mov     rax, [rax+20h]
0x1800c045c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0461  mov     r15d, eax
0x1800c0464  mov     r9d, eax
0x1800c0467  mov     r8, r12
0x1800c046a  lea     rdx, aSCpaudioclient; "[%s] cpAudioClientInternal->Initialize("...
0x1800c0471  mov     ecx, 8; int
0x1800c0476  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800c047b  cmp     r15d, 88890017h
0x1800c0482  jnz     short loc_1800C048F
0x1800c0484  inc     edi
0x1800c0486  cmp     edi, 3
0x1800c0489  jle     loc_1800C0406
0x1800c048f  test    r15d, r15d
0x1800c0492  mov     rbx, [rbp+30h+var_90]
0x1800c0496  js      short loc_1800C04D1
0x1800c0498  mov     rax, 346DC5D63886594Bh
0x1800c04a2  imul    rsi
0x1800c04a5  sar     rdx, 0Bh
0x1800c04a9  mov     rax, rdx
0x1800c04ac  shr     rax, 3Fh
0x1800c04b0  add     rdx, rax
0x1800c04b3  mov     [r14+250h], edx
0x1800c04ba  mov     r9d, edx
0x1800c04bd  mov     r8, r12
0x1800c04c0  lea     rdx, aSBufferDuratio; "[%s] buffer duration %d ms"
0x1800c04c7  mov     ecx, 8; int
  ... truncated ...
```
