# TetheringSessionTelemetry::TetheringSessionTelemetry(ulong)

- ea: `0x180026b10`
- end: `0x180026f93`
- name: `??0TetheringSessionTelemetry@@QEAA@K@Z`
- size: `1155`
- prototype: `TetheringSessionTelemetry *__fastcall(TetheringSessionTelemetry *this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ce60`
- `0x180014c8c`
- `0x180019b4c`

## callees

- `0x180001008`
- `0x180002590`
- `0x180003088`
- `0x180026b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026f6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026f6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026c65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026c65`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180026c5c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180026c5c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026dc2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026ddb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026f10`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026f3e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026f50`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026dc2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026ddb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026f10`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026f3e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026f50`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180026d53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180026d53`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180026f2a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180026f2a`

## pseudocode

```c
TetheringSessionTelemetry *__fastcall TetheringSessionTelemetry::TetheringSessionTelemetry(
        TetheringSessionTelemetry *this,
        int a2)
{
  char *v2; // rbx
  RTL_SRWLOCK *v4; // r13
  ULONGLONG TickCount64; // rax
  unsigned int v6; // ebx
  char *v7; // rsi
  int v8; // eax
  char *v9; // r9
  int v11; // [rsp+30h] [rbp-99h] BYREF
  int v12; // [rsp+34h] [rbp-95h] BYREF
  int v13; // [rsp+38h] [rbp-91h] BYREF
  int v14; // [rsp+3Ch] [rbp-8Dh] BYREF
  int v15; // [rsp+40h] [rbp-89h] BYREF
  GUID ActivityId; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-69h] BYREF
  int *v18; // [rsp+80h] [rbp-49h]
  __int64 v19; // [rsp+88h] [rbp-41h]
  int *v20; // [rsp+90h] [rbp-39h]
  __int64 v21; // [rsp+98h] [rbp-31h]
  int *v22; // [rsp+A0h] [rbp-29h]
  __int64 v23; // [rsp+A8h] [rbp-21h]
  int *v24; // [rsp+B0h] [rbp-19h]
  __int64 v25; // [rsp+B8h] [rbp-11h]
  int *v26; // [rsp+C0h] [rbp-9h]
  __int64 v27; // [rsp+C8h] [rbp-1h]

  *((_DWORD *)this + 17) = a2;
  v2 = (char *)this + 136;
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &TetheringSessionTelemetry::`vftable';
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *(_OWORD *)((char *)this + 236) = 0;
  v4 = (RTL_SRWLOCK *)((char *)this + 16);
  *(_OWORD *)((char *)this + 252) = 0;
  *((_DWORD *)this + 67) = 0;
  *(_OWORD *)((char *)this + 280) = 0;
  *((_QWORD *)this + 38) = 7;
  *((_QWORD *)this + 37) = 0;
  *((_WORD *)this + 140) = 0;
  *(_OWORD *)((char *)this + 312) = 0;
  *((_QWORD *)this + 42) = 7;
  *((_QWORD *)this + 41) = 0;
  *((_WORD *)this + 156) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  *((_QWORD *)this + 46) = 7;
  *((_QWORD *)this + 45) = 0;
  *((_WORD *)this + 172) = 0;
  *(_OWORD *)((char *)this + 376) = 0;
  *((_QWORD *)this + 50) = 7;
  *((_QWORD *)this + 49) = 0;
  *((_WORD *)this + 188) = 0;
  *(_OWORD *)((char *)this + 408) = 0;
  *((_QWORD *)this + 54) = 7;
  *((_QWORD *)this + 53) = 0;
  *((_WORD *)this + 204) = 0;
  *(_OWORD *)((char *)this + 440) = 0;
  *((_QWORD *)this + 58) = 7;
  *((_QWORD *)this + 57) = 0;
  *((_WORD *)this + 220) = 0;
  *(_OWORD *)((char *)this + 472) = 0;
  *((_QWORD *)this + 62) = 7;
  *((_QWORD *)this + 61) = 0;
  *((_WORD *)this + 236) = 0;
  *((_DWORD *)this + 126) = 0;
  *((_BYTE *)this + 508) = 0;
  ActivityId = 0;
  InitializeSRWLock((PSRWLOCK)this + 2);
  AcquireSRWLockExclusive(v4);
  *(_OWORD *)((char *)this + 28) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  memset_0(v2, 0, 0x170u);
  *(_QWORD *)((char *)this + 92) = 0;
  *(_QWORD *)((char *)this + 100) = 0;
  *(_QWORD *)((char *)this + 108) = 0;
  *(_QWORD *)((char *)this + 116) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *((_DWORD *)this + 33) = 0;
  if ( (dword_180041008
     && (qword_180041018 & 0x200000000000LL) != 0
     && (qword_180041020 & 0x200000000000LL) == qword_180041020
     || dword_180041008
     && (qword_180041018 & 0x400000000000LL) != 0
     && (qword_180041020 & 0x400000000000LL) == qword_180041020
     || dword_180041008
     && (qword_180041018 & 0x800000000000LL) != 0
     && (qword_180041020 & 0x800000000000LL) == qword_180041020)
    && g_lTraceLoggingRegistered >= 0 )
  {
    TickCount64 = GetTickCount64();
    v6 = *((_DWORD *)this + 17);
    *((_QWORD *)this + 6) = TickCount64;
    if ( (unsigned int)dword_180041008 > 5
      && (qword_180041018 & 0x400000000000LL) != 0
      && (qword_180041020 & 0x400000000000LL) == qword_180041020 )
    {
      v7 = (char *)this + 512;
      EventActivityIdControl(3u, (LPGUID)this + 32);
      *((_OWORD *)this + 33) = *((_OWORD *)this + 32);
      EventActivityIdControl(4u, (LPGUID)this + 33);
      *((_BYTE *)this + 508) = 1;
    }
    else
    {
      v7 = (char *)this + 512;
      *((_OWORD *)this + 32) = 0;
    }
    *((_DWORD *)this + 126) = 1;
    if ( (unsigned int)dword_180041008 > 5
      && (qword_180041018 & 0x400000000000LL) != 0
      && (qword_180041020 & 0x400000000000LL) == qword_180041020 )
    {
      v8 = *((_DWORD *)this + 17);
      v15 = v6 & 1;
      v11 = v8;
      v12 = (v6 >> 3) & 1;
      v13 = (v6 >> 2) & 1;
      v14 = (v6 >> 1) & 1;
      if ( !*((_BYTE *)this + 508)
        || (v9 = (char *)this + 528, !*((_DWORD *)this + 132))
        && !*((_DWORD *)this + 133)
        && !*((_DWORD *)this + 134)
        && !*((_DWORD *)this + 135) )
      {
        v9 = 0;
      }
      v27 = 4;
      v26 = &v11;
      v25 = 4;
      v24 = &v12;
      v23 = 4;
      v22 = &v13;
      v21 = 4;
      v20 = &v14;
      v18 = &v15;
      v19 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180041008, &word_18003A54E, v7, v9, 7, v17);
    }
    if ( !EventActivityIdControl(1u, &ActivityId)
      && (RtlCompareMemory(&GUID_NULL, &ActivityId, 0x10u) != 16
       || !EventActivityIdControl(3u, &ActivityId) && !EventActivityIdControl(2u, &ActivityId)) )
    {
      *(GUID *)((char *)this + 28) = ActivityId;
    }
    *((_DWORD *)this + 6) = 1;
  }
  ReleaseSRWLockExclusive(v4);
  return this;
}

```

## disassembly

```asm
0x180026b10  push    rbp
0x180026b12  push    rbx
0x180026b13  push    rsi
0x180026b14  push    rdi
0x180026b15  push    r12
0x180026b17  push    r13
0x180026b19  push    r14
0x180026b1b  push    r15
0x180026b1d  lea     rbp, [rsp-1Fh]
0x180026b22  sub     rsp, 0E8h
0x180026b29  mov     rax, cs:__security_cookie
0x180026b30  xor     rax, rsp
0x180026b33  mov     [rbp+57h+var_50], rax
0x180026b37  mov     [rcx+44h], edx
0x180026b3a  lea     rbx, [rcx+88h]
0x180026b41  mov     dword ptr [rcx+8], 1
0x180026b48  lea     rax, ??_7TetheringSessionTelemetry@@6B@; const TetheringSessionTelemetry::`vftable'
0x180026b4f  mov     [rcx], rax
0x180026b52  xor     esi, esi
0x180026b54  mov     [rcx+18h], esi
0x180026b57  xorps   xmm0, xmm0
0x180026b5a  mov     [rcx+30h], rsi
0x180026b5e  mov     rdi, rcx
0x180026b61  mov     [rcx+48h], rsi
0x180026b65  xor     eax, eax
0x180026b67  mov     [rcx+38h], rsi
0x180026b6b  mov     [rcx+40h], esi
0x180026b6e  lea     ecx, [rsi+7]
0x180026b71  movups  xmmword ptr [rbx+64h], xmm0
0x180026b75  lea     r13, [rdi+10h]
0x180026b79  movups  xmmword ptr [rbx+74h], xmm0
0x180026b7d  mov     [rbx+84h], eax
0x180026b83  movups  xmmword ptr [rbx+90h], xmm0
0x180026b8a  mov     [rbx+0A8h], rcx
0x180026b91  mov     [rbx+0A0h], rsi
0x180026b98  mov     [rbx+90h], si
0x180026b9f  movups  xmmword ptr [rbx+0B0h], xmm0
0x180026ba6  mov     [rbx+0C8h], rcx
0x180026bad  mov     [rbx+0C0h], rsi
0x180026bb4  mov     [rbx+0B0h], si
0x180026bbb  movups  xmmword ptr [rbx+0D0h], xmm0
0x180026bc2  mov     [rbx+0E8h], rcx
0x180026bc9  mov     [rbx+0E0h], rsi
0x180026bd0  mov     [rbx+0D0h], si
0x180026bd7  movups  xmmword ptr [rbx+0F0h], xmm0
0x180026bde  mov     [rbx+108h], rcx
0x180026be5  mov     [rbx+100h], rsi
0x180026bec  mov     [rbx+0F0h], si
0x180026bf3  movups  xmmword ptr [rbx+110h], xmm0
0x180026bfa  mov     [rbx+128h], rcx
0x180026c01  mov     [rbx+120h], rsi
0x180026c08  mov     [rbx+110h], si
0x180026c0f  movups  xmmword ptr [rbx+130h], xmm0
0x180026c16  mov     [rbx+148h], rcx
0x180026c1d  mov     [rbx+140h], rsi
0x180026c24  mov     [rbx+130h], si
0x180026c2b  movups  xmmword ptr [rbx+150h], xmm0
0x180026c32  mov     [rbx+168h], rcx
0x180026c39  mov     rcx, r13; SRWLock
0x180026c3c  mov     [rbx+160h], rsi
0x180026c43  mov     [rbx+150h], si
0x180026c4a  mov     [rdi+1F8h], esi
0x180026c50  mov     [rdi+1FCh], sil
0x180026c57  movups  xmmword ptr [rsp+120h+ActivityId.Data1], xmm0
0x180026c5c  call    cs:__imp_InitializeSRWLock
0x180026c62  mov     rcx, r13; SRWLock
0x180026c65  call    cs:__imp_AcquireSRWLockExclusive
0x180026c6b  xor     eax, eax
0x180026c6d  xorps   xmm0, xmm0
0x180026c70  movups  xmmword ptr [rdi+1Ch], xmm0
0x180026c74  mov     [rdi+50h], rax
0x180026c78  xor     edx, edx; Val
0x180026c7a  mov     r8d, 170h; Size
0x180026c80  mov     [rdi+58h], eax
0x180026c83  mov     rcx, rbx; void *
0x180026c86  call    memset_0
0x180026c8b  mov     [rdi+5Ch], rsi
0x180026c8f  mov     rdx, 400000000000h
0x180026c99  mov     [rdi+64h], rsi
0x180026c9d  mov     [rdi+6Ch], rsi
0x180026ca1  mov     [rdi+74h], rsi
0x180026ca5  mov     [rdi+7Ch], rsi
0x180026ca9  mov     [rdi+84h], esi
0x180026caf  mov     eax, cs:dword_180041008
0x180026cb5  test    eax, eax
0x180026cb7  jz      short loc_180026CE1
0x180026cb9  mov     rcx, cs:qword_180041020
0x180026cc0  mov     r8, 200000000000h
0x180026cca  mov     rax, cs:qword_180041018
0x180026cd1  test    r8, rax
0x180026cd4  jz      short loc_180026CE1
0x180026cd6  mov     rax, rcx
0x180026cd9  and     rax, r8
0x180026cdc  cmp     rax, rcx
0x180026cdf  jz      short loc_180026D47
0x180026ce1  mov     eax, cs:dword_180041008
0x180026ce7  test    eax, eax
0x180026ce9  jz      short loc_180026D09
0x180026ceb  mov     rcx, cs:qword_180041020
0x180026cf2  mov     rax, cs:qword_180041018
0x180026cf9  test    rdx, rax
0x180026cfc  jz      short loc_180026D09
0x180026cfe  mov     rax, rcx
0x180026d01  and     rax, rdx
0x180026d04  cmp     rax, rcx
0x180026d07  jz      short loc_180026D47
0x180026d09  mov     eax, cs:dword_180041008
0x180026d0f  test    eax, eax
0x180026d11  jz      loc_180026F67
0x180026d17  mov     rcx, cs:qword_180041020
0x180026d1e  mov     rdx, 800000000000h
0x180026d28  mov     rax, cs:qword_180041018
0x180026d2f  test    rdx, rax
0x180026d32  jz      loc_180026F67
0x180026d38  mov     rax, rcx
0x180026d3b  and     rax, rdx
0x180026d3e  cmp     rax, rcx
0x180026d41  jnz     loc_180026F67
0x180026d47  cmp     cs:?g_lTraceLoggingRegistered@@3JA, esi; long g_lTraceLoggingRegistered
0x180026d4d  jl      loc_180026F67
0x180026d53  call    cs:__imp_GetTickCount64
0x180026d59  mov     ebx, [rdi+44h]
0x180026d5c  mov     r14d, ebx
0x180026d5f  shr     r14d, 1
0x180026d62  mov     r15d, ebx
0x180026d65  shr     r15d, 2
0x180026d69  mov     r12d, ebx
0x180026d6c  shr     r12d, 3
0x180026d70  and     r14d, 1
0x180026d74  and     r15d, 1
0x180026d78  mov     [rdi+30h], rax
0x180026d7c  mov     eax, cs:dword_180041008
0x180026d82  and     r12d, 1
0x180026d86  cmp     eax, 5
0x180026d89  jbe     short loc_180026DEA
0x180026d8b  mov     rcx, cs:qword_180041020
0x180026d92  mov     r8, 400000000000h
0x180026d9c  mov     rax, cs:qword_180041018
0x180026da3  test    r8, rax
0x180026da6  jz      short loc_180026DEA
0x180026da8  mov     rax, rcx
0x180026dab  and     rax, r8
0x180026dae  cmp     rax, rcx
0x180026db1  jnz     short loc_180026DEA
0x180026db3  lea     rsi, [rdi+200h]
0x180026dba  mov     ecx, 3; ControlCode
0x180026dbf  mov     rdx, rsi; ActivityId
0x180026dc2  call    cs:__imp_EventActivityIdControl
0x180026dc8  movups  xmm0, xmmword ptr [rsi]
0x180026dcb  lea     rdx, [rdi+210h]; ActivityId
0x180026dd2  mov     ecx, 4; ControlCode
0x180026dd7  movdqu  xmmword ptr [rdx], xmm0
0x180026ddb  call    cs:__imp_EventActivityIdControl
0x180026de1  mov     byte ptr [rdi+1FCh], 1
0x180026de8  jmp     short loc_180026DF7
0x180026dea  lea     rsi, [rdi+200h]
0x180026df1  xorps   xmm0, xmm0
0x180026df4  movups  xmmword ptr [rsi], xmm0
0x180026df7  mov     dword ptr [rdi+1F8h], 1
0x180026e01  mov     eax, cs:dword_180041008
0x180026e07  cmp     eax, 5
0x180026e0a  jbe     loc_180026F04
0x180026e10  mov     rcx, cs:qword_180041020
0x180026e17  mov     r8, 400000000000h
0x180026e21  mov     rax, cs:qword_180041018
0x180026e28  test    r8, rax
0x180026e2b  jz      loc_180026F04
0x180026e31  mov     rax, rcx
0x180026e34  and     rax, r8
0x180026e37  cmp     rax, rcx
0x180026e3a  jnz     loc_180026F04
0x180026e40  mov     eax, [rdi+44h]
0x180026e43  and     ebx, 1
0x180026e46  mov     [rsp+120h+var_E0], ebx
0x180026e4a  xor     ebx, ebx
0x180026e4c  mov     [rsp+120h+var_F0], eax
0x180026e50  mov     [rsp+120h+var_EC], r12d
0x180026e55  mov     [rsp+120h+var_E8], r15d
0x180026e5a  mov     [rsp+120h+var_E4], r14d
0x180026e5f  cmp     [rdi+1FCh], bl
0x180026e65  jz      short loc_180026E85
0x180026e67  lea     r9, [rdi+210h]
0x180026e6e  cmp     [r9], ebx
0x180026e71  jnz     short loc_180026E88
0x180026e73  cmp     [r9+4], ebx
0x180026e77  jnz     short loc_180026E88
0x180026e79  cmp     [r9+8], ebx
0x180026e7d  jnz     short loc_180026E88
0x180026e7f  cmp     [r9+0Ch], ebx
0x180026e83  jnz     short loc_180026E88
0x180026e85  mov     r9, rbx
0x180026e88  lea     rax, [rsp+120h+var_F0]
0x180026e8d  mov     [rbp+57h+var_58], 4
0x180026e95  mov     [rbp+57h+var_60], rax
0x180026e99  lea     rdx, word_18003A54E
0x180026ea0  lea     rax, [rsp+120h+var_EC]
0x180026ea5  mov     [rbp+57h+var_68], 4
0x180026ead  mov     [rbp+57h+var_70], rax
0x180026eb1  lea     rcx, dword_180041008
0x180026eb8  lea     rax, [rsp+120h+var_E8]
0x180026ebd  mov     [rbp+57h+var_78], 4
0x180026ec5  mov     [rbp+57h+var_80], rax
0x180026ec9  mov     r8, rsi
0x180026ecc  lea     rax, [rsp+120h+var_E4]
0x180026ed1  mov     [rbp+57h+var_88], 4
0x180026ed9  mov     [rbp+57h+var_90], rax
0x180026edd  lea     rax, [rsp+120h+var_E0]
0x180026ee2  mov     [rbp+57h+var_A0], rax
0x180026ee6  lea     rax, [rbp+57h+var_C0]
0x180026eea  mov     [rsp+120h+var_F8], rax
0x180026eef  mov     [rsp+120h+var_100], 7
0x180026ef7  mov     [rbp+57h+var_98], 4
0x180026eff  call    _tlgWriteTransfer_EventWriteTransfer
0x180026f04  mov     esi, 1
0x180026f09  lea     rdx, [rsp+120h+ActivityId]; ActivityId
0x180026f0e  mov     ecx, esi; ControlCode
0x180026f10  call    cs:__imp_EventActivityIdControl
0x180026f16  test    eax, eax
0x180026f18  jnz     short loc_180026F64
0x180026f1a  lea     r8d, [rsi+0Fh]; Length
0x180026f1e  lea     rdx, [rsp+120h+ActivityId]; Source2
0x180026f23  lea     rcx, GUID_NULL; Source1
0x180026f2a  call    cs:__imp_RtlCompareMemory
0x180026f30  cmp     rax, 10h
0x180026f34  jnz     short loc_180026F5A
0x180026f36  lea     rdx, [rsp+120h+ActivityId]; ActivityId
0x180026f3b  lea     ecx, [rsi+2]; ControlCode
0x180026f3e  call    cs:__imp_EventActivityIdControl
0x180026f44  test    eax, eax
0x180026f46  jnz     short loc_180026F64
0x180026f48  lea     rdx, [rsp+120h+ActivityId]; ActivityId
0x180026f4d  lea     ecx, [rsi+1]; ControlCode
0x180026f50  call    cs:__imp_EventActivityIdControl
0x180026f56  test    eax, eax
0x180026f58  jnz     short loc_180026F64
0x180026f5a  movups  xmm0, xmmword ptr [rsp+120h+ActivityId.Data1]
0x180026f5f  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x180026f64  mov     [rdi+18h], esi
0x180026f67  mov     rcx, r13; SRWLock
0x180026f6a  call    cs:__imp_ReleaseSRWLockExclusive
0x180026f70  mov     rax, rdi
0x180026f73  mov     rcx, [rbp+57h+var_50]
0x180026f77  xor     rcx, rsp; StackCookie
0x180026f7a  call    __security_check_cookie
0x180026f7f  add     rsp, 0E8h
0x180026f86  pop     r15
0x180026f88  pop     r14
0x180026f8a  pop     r13
0x180026f8c  pop     r12
0x180026f8e  pop     rdi
0x180026f8f  pop     rsi
0x180026f90  pop     rbx
0x180026f91  pop     rbp
0x180026f92  retn
```
