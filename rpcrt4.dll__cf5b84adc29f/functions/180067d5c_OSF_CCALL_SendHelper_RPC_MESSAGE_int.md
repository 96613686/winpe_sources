# OSF_CCALL::SendHelper(_RPC_MESSAGE *,int *)

- ea: `0x180067d5c`
- end: `0x18006832f`
- name: `?SendHelper@OSF_CCALL@@QEAAJPEAU_RPC_MESSAGE@@PEAH@Z`
- size: `1491`
- prototype: `__int64 __fastcall(OSF_CCALL *__hidden this, struct _RPC_MESSAGE *, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180067308`

## callees

- `0x1800162e0`
- `0x180022e80`
- `0x18002cab0`
- `0x180034eb4`
- `0x18005e47c`
- `0x180066718`
- `0x180066ffc`
- `0x180067798`
- `0x180067d5c`
- `0x180068338`
- `0x180068390`
- `0x180068818`
- `0x1800688d8`
- `0x1800692a4`
- `0x1800a72e0`
- `0x1800b02b4`
- `0x1800b11f0`
- `0x1800cec91`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180067e44`
- `ntdll!RtlLeaveCriticalSection` at `0x180067f5e`
- `ntdll!RtlLeaveCriticalSection` at `0x180067ff4`
- `ntdll!RtlLeaveCriticalSection` at `0x180068090`
- `ntdll!RtlLeaveCriticalSection` at `0x1800680db`
- `ntdll!RtlLeaveCriticalSection` at `0x180068191`
- `ntdll!RtlLeaveCriticalSection` at `0x18006821a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800682d7`
- `ntdll!RtlLeaveCriticalSection` at `0x180067e44`
- `ntdll!RtlLeaveCriticalSection` at `0x180067f5e`
- `ntdll!RtlLeaveCriticalSection` at `0x180067ff4`
- `ntdll!RtlLeaveCriticalSection` at `0x180068090`
- `ntdll!RtlLeaveCriticalSection` at `0x1800680db`
- `ntdll!RtlLeaveCriticalSection` at `0x180068191`
- `ntdll!RtlLeaveCriticalSection` at `0x18006821a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800682d7`
- `ntdll!RtlEnterCriticalSection` at `0x180067de5`
- `ntdll!RtlEnterCriticalSection` at `0x180067e93`
- `ntdll!RtlEnterCriticalSection` at `0x18006815c`
- `ntdll!RtlEnterCriticalSection` at `0x180067de5`
- `ntdll!RtlEnterCriticalSection` at `0x180067e93`
- `ntdll!RtlEnterCriticalSection` at `0x18006815c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18006811e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18006811e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180068110`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180068110`

## pseudocode

```c
__int64 __fastcall OSF_CCALL::SendHelper(OSF_CCALL *this, struct _RPC_MESSAGE *a2, int *a3)
{
  int v3; // r12d
  _QWORD *v7; // r15
  struct _RTL_CRITICAL_SECTION *v8; // rbp
  size_t v9; // r14
  unsigned int v10; // ebx
  void *Buffer; // r15
  unsigned int BufferLength; // r12d
  unsigned int v13; // eax
  OSF_CCALL **v14; // rcx
  int v15; // eax
  unsigned int v16; // eax
  int v17; // ecx
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  __int64 result; // rax
  __int64 v20; // rbp
  int v21; // ebp
  int v22; // edx
  char *v23; // rbx
  DWORD CurrentProcessId; // edi
  unsigned int CommandLineW; // eax
  int v26; // ebx
  int v27; // eax
  _DWORD *v28; // rbx
  unsigned int v29; // r14d
  signed int v30; // edx
  unsigned int BufferDo; // eax
  int v32; // [rsp+28h] [rbp-60h]
  int v33; // [rsp+30h] [rbp-58h]
  void *v34; // [rsp+A0h] [rbp+18h] BYREF
  void *v35; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  v34 = 0;
  *a3 = 0;
  if ( !*((_DWORD *)this + 127) )
    *((_DWORD *)this + 127) = a2->BufferLength;
  v7 = (_QWORD *)((char *)this + 24);
  if ( (a2->RpcFlags & 0x2000) == 0 )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
    *((_QWORD *)this + 52) = a2->Buffer;
    LODWORD(v9) = 0;
    v10 = 0;
    goto LABEL_5;
  }
  if ( !*v7 && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 34) + 408LL) + 256LL) )
  {
    if ( !(unsigned int)ShouldSkipLogging(2u) && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
    {
      v23 = (char *)a2->RpcInterfaceInformation + 4;
      CurrentProcessId = GetCurrentProcessId();
      CommandLineW = (unsigned int)GetCommandLineW();
      McTemplateU0zdzj_EtwEventWriteTransfer(
        (unsigned int)L"ncacn_http",
        (unsigned int)RPC_EVENTLOG_SYNC_PIPE_USE_ERR,
        CommandLineW,
        CurrentProcessId,
        (__int64)L"ncacn_http",
        (__int64)v23);
    }
    v10 = 1764;
    v22 = 1764;
    goto LABEL_47;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 464));
  if ( *v7 || *((_DWORD *)this + 80) )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 464));
  }
  else
  {
    v26 = *((_DWORD *)this + 66);
    *((_DWORD *)this + 153) = 1;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 464));
    if ( v26 == 2 )
    {
      REFERENCED_OBJECT::AddReference(this);
      v27 = OSF_CCONNECTION::AddCall(*((OSF_CCONNECTION **)this + 34), this);
      v28 = (_DWORD *)*((_QWORD *)this + 34);
      v29 = v27;
      LogEvent(0x6Eu, 0x63u, v28, 0, 0, v32, v33);
      v28[26] = 0;
      if ( v29 || (v29 = OSF_CCALL::SendAlterContextPDU(this)) != 0 )
      {
        (*(void (__fastcall **)(OSF_CCALL *))(*(_QWORD *)this + 32LL))(this);
        return v29;
      }
    }
    EVENT::Wait((OSF_CCALL *)((char *)this + 424), -1);
  }
  result = OSF_CCALL::CheckPipeSendForIncompleteBuffer(this, a2);
  v10 = result;
  if ( !(_DWORD)result )
  {
    v30 = a2->BufferLength % *((_DWORD *)this + 90);
    v9 = v30;
    if ( v30 )
    {
      BufferDo = OSF_CCALL::GetBufferDo(this, v30, &v34);
      v10 = BufferDo;
      if ( BufferDo )
      {
        v22 = BufferDo;
LABEL_47:
        OSF_CCALL::CallFailed(this, v22, 0, 0);
        OSF_CCALL::UnregisterCallForCancels(this);
        return v10;
      }
      a2->BufferLength -= v9;
      memcpy_0(v34, (char *)a2->Buffer + a2->BufferLength, v9);
    }
LABEL_5:
    v35 = 0;
    REFERENCED_OBJECT::AddReference(this);
    while ( 1 )
    {
      if ( *((_DWORD *)this + 8) != 997 )
      {
        v10 = *((_DWORD *)this + 8);
        if ( v10 == 1727 )
        {
          if ( v3 )
            v10 = 1726;
        }
        else if ( ((v10 + 1073606648) & 0xFFFFFFF5) == 0 && v10 != -1073606640 || v10 == 1726 && !v3 )
        {
          v10 = 1727;
        }
        if ( *(OSF_CCALL **)(*((_QWORD *)this + 34) + 32LL) != this )
          REFERENCED_OBJECT::RemoveReference(this);
LABEL_20:
        Buffer = v35;
        BufferLength = (unsigned int)v35;
        goto LABEL_21;
      }
      RtlEnterCriticalSection(v8);
      if ( !*((_QWORD *)this + 39) )
        break;
      if ( *v7 || *((int *)this + 135) < 4 )
      {
        if ( (unsigned int)QUEUE::PutOnQueue((OSF_CCALL *)((char *)this + 528), a2->Buffer, a2->BufferLength) )
        {
          v10 = 14;
          if ( *(OSF_CCALL **)(*((_QWORD *)this + 34) + 32LL) != this )
            REFERENCED_OBJECT::RemoveReference(this);
        }
        else
        {
          a2->Buffer = 0;
          a2->BufferLength = 0;
        }
        RtlLeaveCriticalSection(v8);
        goto LABEL_20;
      }
      v3 = 1;
      *((_DWORD *)this + 153) = 1;
      RtlLeaveCriticalSection(v8);
      EVENT::Wait((OSF_CCALL *)((char *)this + 424), -1);
    }
    *((_DWORD *)this + 81) = 0;
    *((_QWORD *)this + 39) = a2->Buffer;
    *((_DWORD *)this + 82) = a2->BufferLength;
    Buffer = a2->Buffer;
    BufferLength = a2->BufferLength;
    a2->Buffer = 0;
    a2->BufferLength = 0;
    if ( !*((_DWORD *)this + 85) )
    {
      RtlLeaveCriticalSection(v8);
      goto LABEL_11;
    }
    ++*((_DWORD *)this + 128);
    *((_DWORD *)this + 85) = 0;
    RtlLeaveCriticalSection(v8);
    v13 = OSF_CCALL::RegisterCallForCancels(this);
    v14 = (OSF_CCALL **)*((_QWORD *)this + 34);
    v10 = v13;
    if ( !v13 )
    {
      v15 = OSF_CCONNECTION::AddCall((OSF_CCONNECTION *)v14, this);
      *a3 = 1;
      v10 = v15;
      if ( v15 )
      {
        if ( *(OSF_CCALL **)(*((_QWORD *)this + 34) + 32LL) != this )
          goto LABEL_40;
        goto LABEL_41;
      }
LABEL_11:
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 34) + 216LL));
      v16 = *((_DWORD *)this + 66);
      if ( v16 <= 0xC )
      {
        v17 = 6720;
        if ( _bittest(&v17, v16) )
        {
          v18 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 34) + 216LL);
          goto LABEL_29;
        }
      }
      v20 = *((_QWORD *)this + 34);
      if ( *(OSF_CCALL **)(v20 + 32) == this && *(_DWORD *)(v20 + 104) )
      {
        LogEvent(0x6Eu, 0x63u, (void *)v20, 0, 0, v32, v33);
        *(_DWORD *)(v20 + 104) = 0;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 34) + 216LL));
        v10 = OSF_CCALL::SendData(this, 0);
        if ( !v10 )
        {
LABEL_22:
          if ( (_DWORD)v9 )
          {
            v10 = 1913;
            a2->Buffer = v34;
            a2->BufferLength = v9;
            *((_DWORD *)this + 108) = v9;
          }
          else
          {
            *((_DWORD *)this + 108) = 0;
          }
          goto LABEL_24;
        }
LABEL_40:
        REFERENCED_OBJECT::RemoveReference(this);
LABEL_41:
        v21 = 0;
        goto LABEL_33;
      }
      v18 = (struct _RTL_CRITICAL_SECTION *)(v20 + 216);
LABEL_29:
      RtlLeaveCriticalSection(v18);
LABEL_21:
      if ( !v10 )
        goto LABEL_22;
      goto LABEL_41;
    }
    v21 = 1;
    if ( v14[4] != this )
      REFERENCED_OBJECT::RemoveReference(this);
LABEL_33:
    if ( (_DWORD)v9 )
      OSF_CCALL::FreeBufferDo(this, v34);
    *((_DWORD *)this + 8) = v10;
    if ( !v21 )
      OSF_CCALL::UnregisterCallForCancels(this);
    if ( Buffer )
    {
      a2->Buffer = Buffer;
      a2->BufferLength = BufferLength;
    }
LABEL_24:
    REFERENCED_OBJECT::RemoveReference(this);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180067d5c  mov     rax, rsp
0x180067d5f  push    rbx
0x180067d60  push    rbp
0x180067d61  push    rsi
0x180067d62  push    rdi
0x180067d63  push    r12
0x180067d65  push    r13
0x180067d67  push    r14
0x180067d69  push    r15
0x180067d6b  sub     rsp, 48h
0x180067d6f  xor     r12d, r12d
0x180067d72  mov     r13, r8
0x180067d75  mov     rdi, rdx
0x180067d78  mov     rsi, rcx
0x180067d7b  mov     [rax+18h], r12
0x180067d7f  mov     [r8], r12d
0x180067d82  cmp     [rcx+1FCh], r12d
0x180067d89  jnz     short loc_180067D94
0x180067d8b  mov     eax, [rdx+18h]
0x180067d8e  mov     [rcx+1FCh], eax
0x180067d94  test    dword ptr [rdx+48h], 2000h
0x180067d9b  lea     r15, [rcx+18h]
0x180067d9f  jnz     loc_180068005
0x180067da5  mov     rax, [rdx+10h]
0x180067da9  lea     rbp, [rcx+1D0h]
0x180067db0  mov     [rcx+1A0h], rax
0x180067db7  mov     r14d, r12d
0x180067dba  mov     ebx, r12d
0x180067dbd  mov     rcx, rsi; this
0x180067dc0  mov     [rsp+88h+arg_0], r12d
0x180067dc8  mov     [rsp+88h+arg_18], r12
0x180067dd0  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180067dd5  cmp     dword ptr [rsi+20h], 3E5h
0x180067ddc  jnz     loc_180067ECB
0x180067de2  mov     rcx, rbp; CriticalSection
0x180067de5  call    cs:__imp_RtlEnterCriticalSection
0x180067dec  nop     dword ptr [rax+rax+00h]
0x180067df1  xor     ecx, ecx
0x180067df3  cmp     [rsi+138h], rcx
0x180067dfa  jnz     loc_1800680B5
0x180067e00  mov     [rsi+144h], ecx
0x180067e06  mov     rax, [rdi+10h]
0x180067e0a  mov     [rsi+138h], rax
0x180067e11  mov     eax, [rdi+18h]
0x180067e14  mov     [rsi+148h], eax
0x180067e1a  mov     r15, [rdi+10h]
0x180067e1e  mov     r12d, [rdi+18h]
0x180067e22  mov     [rdi+10h], rcx
0x180067e26  mov     [rdi+18h], ecx
0x180067e29  cmp     [rsi+154h], ecx
0x180067e2f  jz      loc_180067FF1
0x180067e35  inc     dword ptr [rsi+200h]
0x180067e3b  mov     [rsi+154h], ecx
0x180067e41  mov     rcx, rbp; CriticalSection
0x180067e44  call    cs:__imp_RtlLeaveCriticalSection
0x180067e4b  nop     dword ptr [rax+rax+00h]
0x180067e50  mov     rcx, rsi; this
0x180067e53  call    ?RegisterCallForCancels@OSF_CCALL@@AEAAJXZ; OSF_CCALL::RegisterCallForCancels(void)
0x180067e58  mov     rcx, [rsi+110h]; this
0x180067e5f  mov     ebx, eax
0x180067e61  test    eax, eax
0x180067e63  jnz     loc_180067F8A
0x180067e69  mov     rdx, rsi; struct OSF_CCALL *
0x180067e6c  call    ?AddCall@OSF_CCONNECTION@@QEAAJPEAVOSF_CCALL@@@Z; OSF_CCONNECTION::AddCall(OSF_CCALL *)
0x180067e71  mov     dword ptr [r13+0], 1
0x180067e79  mov     ebx, eax
0x180067e7b  test    eax, eax
0x180067e7d  jnz     loc_180067FD3
0x180067e83  mov     rcx, [rsi+110h]
0x180067e8a  mov     r13d, 0D8h
0x180067e90  add     rcx, r13; CriticalSection
0x180067e93  call    cs:__imp_RtlEnterCriticalSection
0x180067e9a  nop     dword ptr [rax+rax+00h]
0x180067e9f  mov     eax, [rsi+108h]
0x180067ea5  cmp     eax, 0Ch
0x180067ea8  ja      loc_180067F46
0x180067eae  mov     ecx, 1A40h
0x180067eb3  bt      ecx, eax
0x180067eb6  jnb     loc_180067F46
0x180067ebc  mov     rcx, [rsi+110h]
0x180067ec3  add     rcx, r13
0x180067ec6  jmp     loc_180067F5E
0x180067ecb  mov     ebx, [rsi+20h]
0x180067ece  mov     ecx, 6BFh
0x180067ed3  cmp     ebx, ecx
0x180067ed5  jz      loc_1800682F5
0x180067edb  lea     eax, [rbx+3FFDEFF8h]
0x180067ee1  test    eax, 0FFFFFFF5h
0x180067ee6  jnz     loc_180068308
0x180067eec  cmp     ebx, 0C0021010h
0x180067ef2  jz      loc_180068308
0x180067ef8  mov     ebx, ecx
0x180067efa  mov     rax, [rsi+110h]
0x180067f01  cmp     [rax+20h], rsi
0x180067f05  jnz     loc_180068322
0x180067f0b  mov     r15, [rsp+88h+arg_18]
0x180067f13  mov     r12d, r15d
0x180067f16  test    ebx, ebx
0x180067f18  jnz     loc_180067FE8
0x180067f1e  test    r14d, r14d
0x180067f21  jnz     short loc_180067F6C
0x180067f23  mov     [rsi+1B0h], r14d
0x180067f2a  mov     rcx, rsi; this
0x180067f2d  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x180067f32  mov     eax, ebx
0x180067f34  add     rsp, 48h
0x180067f38  pop     r15
0x180067f3a  pop     r14
0x180067f3c  pop     r13
0x180067f3e  pop     r12
0x180067f40  pop     rdi
0x180067f41  pop     rsi
0x180067f42  pop     rbp
0x180067f43  pop     rbx
0x180067f44  retn
0x180067f46  mov     rbp, [rsi+110h]
0x180067f4d  cmp     [rbp+20h], rsi
0x180067f51  jz      loc_18006805D
0x180067f57  lea     rcx, [rbp+0D8h]; CriticalSection
0x180067f5e  call    cs:__imp_RtlLeaveCriticalSection
0x180067f65  nop     dword ptr [rax+rax+00h]
0x180067f6a  jmp     short loc_180067F16
0x180067f6c  mov     rax, [rsp+88h+arg_10]
0x180067f74  mov     ebx, 779h
0x180067f79  mov     [rdi+10h], rax
0x180067f7d  mov     [rdi+18h], r14d
0x180067f81  mov     [rsi+1B0h], r14d
0x180067f88  jmp     short loc_180067F2A
0x180067f8a  mov     ebp, 1
0x180067f8f  cmp     [rcx+20h], rsi
0x180067f93  jnz     loc_1800682E8
0x180067f99  test    r14d, r14d
0x180067f9c  jz      short loc_180067FAE
0x180067f9e  mov     rdx, [rsp+88h+arg_10]; void *
0x180067fa6  mov     rcx, rsi; this
0x180067fa9  call    ?FreeBufferDo@OSF_CCALL@@QEAAXPEAX@Z; OSF_CCALL::FreeBufferDo(void *)
0x180067fae  mov     [rsi+20h], ebx
0x180067fb1  test    ebp, ebp
0x180067fb3  jnz     short loc_180067FBD
0x180067fb5  mov     rcx, rsi; this
0x180067fb8  call    ?UnregisterCallForCancels@OSF_CCALL@@AEAAXXZ; OSF_CCALL::UnregisterCallForCancels(void)
0x180067fbd  test    r15, r15
0x180067fc0  jz      loc_180067F2A
0x180067fc6  mov     [rdi+10h], r15
0x180067fca  mov     [rdi+18h], r12d
0x180067fce  jmp     loc_180067F2A
0x180067fd3  mov     rax, [rsi+110h]
0x180067fda  cmp     [rax+20h], rsi
0x180067fde  jz      short loc_180067FE8
0x180067fe0  mov     rcx, rsi; this
0x180067fe3  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x180067fe8  mov     ebp, [rsp+88h+arg_0]
0x180067fef  jmp     short loc_180067F99
0x180067ff1  mov     rcx, rbp; CriticalSection
0x180067ff4  call    cs:__imp_RtlLeaveCriticalSection
0x180067ffb  nop     dword ptr [rax+rax+00h]
0x180068000  jmp     loc_180067E83
0x180068005  cmp     [r15], r12
0x180068008  jnz     loc_180068152
0x18006800e  mov     rax, [rcx+110h]
0x180068015  mov     rcx, [rax+198h]
0x18006801c  cmp     [rcx+100h], r12
0x180068023  jz      loc_180068152
0x180068029  mov     ecx, 2; unsigned int
0x18006802e  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x180068033  test    eax, eax
0x180068035  jz      loc_1800680FB
0x18006803b  mov     ebx, 6E4h
0x180068040  mov     edx, ebx; int
0x180068042  xor     r9d, r9d; int
0x180068045  xor     r8d, r8d; int
0x180068048  mov     rcx, rsi; this
0x18006804b  call    ?CallFailed@OSF_CCALL@@AEAAXJHH@Z; OSF_CCALL::CallFailed(long,int,int)
0x180068050  mov     rcx, rsi; this
0x180068053  call    ?UnregisterCallForCancels@OSF_CCALL@@AEAAXXZ; OSF_CCALL::UnregisterCallForCancels(void)
0x180068058  jmp     loc_180067F32
0x18006805d  cmp     dword ptr [rbp+68h], 0
0x180068061  jz      loc_180067F57
0x180068067  xor     r9d, r9d; void *
0x18006806a  mov     [rsp+88h+var_68], 0; unsigned __int64
0x180068073  mov     r8, rbp; void *
0x180068076  mov     dl, 63h ; 'c'; unsigned __int8
0x180068078  mov     cl, 6Eh ; 'n'; unsigned __int8
0x18006807a  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18006807f  mov     dword ptr [rbp+68h], 0
0x180068086  mov     rcx, [rsi+110h]
0x18006808d  add     rcx, r13; CriticalSection
0x180068090  call    cs:__imp_RtlLeaveCriticalSection
0x180068097  nop     dword ptr [rax+rax+00h]
0x18006809c  xor     edx, edx; unsigned __int8 *
0x18006809e  mov     rcx, rsi; this
0x1800680a1  call    ?SendData@OSF_CCALL@@QEAAJPEAE@Z; OSF_CCALL::SendData(uchar *)
0x1800680a6  mov     ebx, eax
0x1800680a8  test    eax, eax
0x1800680aa  jnz     loc_180067FE0
0x1800680b0  jmp     loc_180067F1E
0x1800680b5  cmp     [r15], rcx
0x1800680b8  jnz     loc_180068291
0x1800680be  cmp     dword ptr [rsi+21Ch], 4
0x1800680c5  jl      loc_180068291
0x1800680cb  mov     r12d, 1
0x1800680d1  mov     rcx, rbp; CriticalSection
0x1800680d4  mov     [rsi+264h], r12d
0x1800680db  call    cs:__imp_RtlLeaveCriticalSection
0x1800680e2  nop     dword ptr [rax+rax+00h]
0x1800680e7  lea     rcx, [rsi+1A8h]; this
0x1800680ee  or      edx, 0FFFFFFFFh; int
0x1800680f1  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x1800680f6  jmp     loc_180067DD5
0x1800680fb  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x180068102  jz      loc_18006803B
0x180068108  mov     rbx, [rdi+28h]
0x18006810c  add     rbx, 4
0x180068110  call    cs:__imp_GetCurrentProcessId
0x180068117  nop     dword ptr [rax+rax+00h]
0x18006811c  mov     edi, eax
0x18006811e  call    cs:__imp_GetCommandLineW
0x180068125  nop     dword ptr [rax+rax+00h]
0x18006812a  lea     rcx, aNcacnHttp; "ncacn_http"
0x180068131  mov     [rsp+88h+var_60], rbx
0x180068136  mov     r8, rax
0x180068139  mov     [rsp+88h+var_68], rcx
0x18006813e  mov     r9d, edi
0x180068141  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x180068148  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x18006814d  jmp     loc_18006803B
0x180068152  lea     rbp, [rsi+1D0h]
0x180068159  mov     rcx, rbp; CriticalSection
0x18006815c  call    cs:__imp_RtlEnterCriticalSection
0x180068163  nop     dword ptr [rax+rax+00h]
0x180068168  cmp     [r15], r12
0x18006816b  jnz     loc_180068217
0x180068171  cmp     [rsi+140h], r12d
0x180068178  jnz     loc_180068217
0x18006817e  mov     ebx, [rsi+108h]
0x180068184  mov     rcx, rbp; CriticalSection
0x180068187  mov     dword ptr [rsi+264h], 1
0x180068191  call    cs:__imp_RtlLeaveCriticalSection
0x180068198  nop     dword ptr [rax+rax+00h]
0x18006819d  cmp     ebx, 2
0x1800681a0  jnz     short loc_180068206
0x1800681a2  mov     rcx, rsi; this
0x1800681a5  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x1800681aa  mov     rcx, [rsi+110h]; this
0x1800681b1  mov     rdx, rsi; struct OSF_CCALL *
0x1800681b4  call    ?AddCall@OSF_CCONNECTION@@QEAAJPEAVOSF_CCALL@@@Z; OSF_CCONNECTION::AddCall(OSF_CCALL *)
0x1800681b9  mov     rbx, [rsi+110h]
0x1800681c0  xor     r9d, r9d; void *
0x1800681c3  mov     r8, rbx; void *
0x1800681c6  mov     [rsp+88h+var_68], r12; unsigned __int64
0x1800681cb  mov     dl, 63h ; 'c'; unsigned __int8
0x1800681cd  mov     cl, 6Eh ; 'n'; unsigned __int8
0x1800681cf  mov     r14d, eax
0x1800681d2  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800681d7  mov     [rbx+68h], r12d
0x1800681db  test    r14d, r14d
0x1800681de  jnz     short loc_1800681EF
0x1800681e0  mov     rcx, rsi; this
0x1800681e3  call    ?SendAlterContextPDU@OSF_CCALL@@AEAAJXZ; OSF_CCALL::SendAlterContextPDU(void)
0x1800681e8  mov     r14d, eax
0x1800681eb  test    eax, eax
0x1800681ed  jz      short loc_180068206
0x1800681ef  mov     rax, [rsi]
0x1800681f2  mov     rcx, rsi
0x1800681f5  mov     rax, [rax+20h]
0x1800681f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681fe  mov     eax, r14d
0x180068201  jmp     loc_180067F34
0x180068206  lea     rcx, [rsi+1A8h]; this
0x18006820d  or      edx, 0FFFFFFFFh; int
0x180068210  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x180068215  jmp     short loc_180068226
0x180068217  mov     rcx, rbp; CriticalSection
0x18006821a  call    cs:__imp_RtlLeaveCriticalSection
0x180068221  nop     dword ptr [rax+rax+00h]
0x180068226  mov     rdx, rdi; struct _RPC_MESSAGE *
0x180068229  mov     rcx, rsi; this
0x18006822c  call    ?CheckPipeSendForIncompleteBuffer@OSF_CCALL@@QEAAJPEAU_RPC_MESSAGE@@@Z; OSF_CCALL::CheckPipeSendForIncompleteBuffer(_RPC_MESSAGE *)
0x180068231  mov     ebx, eax
0x180068233  test    eax, eax
0x180068235  jnz     loc_180067F34
0x18006823b  mov     eax, [rdi+18h]
0x18006823e  xor     edx, edx
0x180068240  div     dword ptr [rsi+168h]
0x180068246  movsxd  r14, edx
0x180068249  test    edx, edx
0x18006824b  jz      loc_180067DBD
0x180068251  lea     r8, [rsp+88h+arg_10]; void **
0x180068259  mov     edx, r14d; unsigned int
0x18006825c  mov     rcx, rsi; this
0x18006825f  call    ?GetBufferDo@OSF_CCALL@@QEAAJIPEAPEAX@Z; OSF_CCALL::GetBufferDo(uint,void * *)
0x180068264  mov     ebx, eax
0x180068266  test    eax, eax
0x180068268  jz      short loc_180068271
0x18006826a  mov     edx, eax
0x18006826c  jmp     loc_180068042
0x180068271  sub     [rdi+18h], r14d
0x180068275  mov     r8, r14; Size
0x180068278  mov     edx, [rdi+18h]
0x18006827b  add     rdx, [rdi+10h]; Src
  ... truncated ...
```
