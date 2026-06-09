# AgCxContextNotify

- ea: `0x180060d50`
- end: `0x180061145`
- name: `AgCxContextNotify`
- size: `1013`
- prototype: `__int64 __fastcall(__int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x180060d50`

## callees

- `0x180035dd4`
- `0x18003cbe4`
- `0x18003cffc`
- `0x18005e298`
- `0x18005f708`
- `0x180060d50`
- `0x18008a168`
- `0x180090134`
- `0x1800a9c18`
- `0x1800aa484`
- `0x1800aa7e0`
- `0x1800ab038`
- `0x1800ab17c`
- `0x1800ab51c`
- `0x1800ab5d8`
- `0x1800ab6ac`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180060df4`
- `ntdll!NtQueryInformationThread` at `0x180060df4`
- `ntdll!RtlNtStatusToDosError` at `0x180060e00`
- `ntdll!RtlNtStatusToDosError` at `0x180060e00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060e2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180060e2d`

## pseudocode

```c
__int64 __fastcall AgCxContextNotify(__int64 a1, int a2, _DWORD *a3)
{
  __int64 v3; // rsi
  unsigned int v4; // edi
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  __int64 v12; // rdx
  HANDLE CurrentThread; // rax
  int v15; // eax
  int v16; // ebx
  HANDLE v17; // rax
  HANDLE v18; // rax
  struct _RTL_CRITICAL_SECTION *v19; // r10
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdi
  bool v23; // zf
  __int64 v24; // rdx
  int ThreadInformation; // [rsp+58h] [rbp+10h] BYREF
  __int64 v27; // [rsp+68h] [rbp+20h]

  v3 = a1;
  if ( a2 > 9 )
  {
    if ( a2 == 10 )
    {
      switch ( *a3 )
      {
        case 1:
          v24 = 1;
          break;
        case 2:
          BtDbDatabaseCleanup(a1 + 3440);
          PfSpDbInitialize((void *)(v3 + 3440));
          AgCxSnapshotBuild(v3, v3 + 3440, 0, 0xFFFFFFFFLL);
          v24 = 2;
          break;
        case 3:
          v24 = 3;
          break;
        case 4:
          if ( *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1872LL) != -1 )
            return 0;
          AgCxKnownContextStart(a1, 4);
          v12 = 4;
          goto LABEL_43;
        case 5:
          v24 = 5;
          break;
        default:
          return 1359;
      }
      return (unsigned int)AgCxKnownContextStart(v3, v24);
    }
    if ( a2 != 11 && a2 != 12 )
    {
      switch ( a2 )
      {
        case 13:
          AgCxKnownContextStartPhase(a1, 4);
          break;
        case 14:
          v12 = 4;
          goto LABEL_43;
        case 15:
          v20 = 4;
          return (unsigned int)AgCxKnownContextEnd(a1, v20, 1);
        case 16:
          break;
        case 17:
          v20 = 5;
          return (unsigned int)AgCxKnownContextEnd(a1, v20, 1);
        case 18:
          return (unsigned int)AgCxUserLazyDisconnect(a1, a3);
        default:
          return 1359;
      }
      v12 = 5;
LABEL_43:
      a1 = v3;
      return (unsigned int)AgCxKnownContextStartPhase(a1, v12);
    }
    switch ( *a3 )
    {
      case 1:
        v23 = a2 == 12;
        v12 = 1;
        if ( !v23 )
          return (unsigned int)AgCxKnownContextStartPhase(a1, v12);
        break;
      case 2:
        if ( a2 == 12 )
        {
          v12 = 3;
          v22 = 0;
        }
        else
        {
          AgCxKnownContextStartPhase(a1, 2);
          v12 = 2;
          v22 = 1;
        }
        v21 = v22;
        goto LABEL_58;
      case 3:
        if ( a2 != 12 )
          goto LABEL_12;
        v12 = 9;
        break;
      case 4:
        v12 = 15 - (unsigned int)(a2 != 12);
        v21 = 0;
LABEL_58:
        a1 = v3;
        return (unsigned int)AgCxContextNotify(a1, v12, v21);
      case 5:
        if ( a2 != 12 )
        {
          v12 = 5;
          return (unsigned int)AgCxKnownContextStartPhase(a1, v12);
        }
        v12 = 17;
        break;
      default:
        return 1359;
    }
    v21 = 0;
    return (unsigned int)AgCxContextNotify(a1, v12, v21);
  }
  if ( a2 == 9 )
  {
    v20 = 3;
    return (unsigned int)AgCxKnownContextEnd(a1, v20, 1);
  }
  v4 = 0;
  if ( !a2 )
  {
    v12 = 1;
    return (unsigned int)AgCxKnownContextStartPhase(a1, v12);
  }
  v5 = a2 - 1;
  if ( !v5 )
  {
    v20 = 1;
    return (unsigned int)AgCxKnownContextEnd(a1, v20, 1);
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    if ( !(_DWORD)a3 )
    {
      v12 = 2;
      return (unsigned int)AgCxKnownContextStartPhase(a1, v12);
    }
    v4 = AgCxSnapshotRestore(
           a1,
           0,
           *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 240LL)
         + (unsigned int)((unsigned __int64)((((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64) >> 10),
           (int)a1 + 3440,
           4);
    BtDbDatabaseCleanup(v3 + 3440);
    PfSpDbInitialize((void *)(v3 + 3440));
    return v4;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v20 = 2;
    return (unsigned int)AgCxKnownContextEnd(a1, v20, 1);
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( !v9 )
      return (unsigned int)AgCxUserConnect(a1, (unsigned int)a3);
    v10 = v9 - 1;
    if ( !v10 )
      return (unsigned int)AgCxUserDisconnect();
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 == 1 )
      {
LABEL_12:
        v12 = 3;
        return (unsigned int)AgCxKnownContextStartPhase(a1, v12);
      }
      return 1359;
    }
    CurrentThread = GetCurrentThread();
    ThreadInformation = 0;
    v15 = NtQueryInformationThread(CurrentThread, ThreadIoPriority, &ThreadInformation, 4u, 0);
    if ( v15 >= 0 )
    {
      v16 = ThreadInformation;
    }
    else
    {
      RtlNtStatusToDosError(v15);
      v16 = 5;
    }
    v17 = GetCurrentThread();
    PfSetIoPriorityThread(v17);
    v4 = AgCxFilesCleanup();
    if ( v16 != 5 )
    {
      v18 = GetCurrentThread();
      PfSetIoPriorityThread(v18);
    }
    v27 = PfsActionItemGetCurrentTime() + 864000000000LL;
    PfsActionItemQueueEx(v19 + 43);
  }
  else
  {
    AgCxPrefetchEndCheck(a1, a1 + 14912);
  }
  return v4;
}

```

## disassembly

```asm
0x180060d50  mov     [rsp+arg_0], rbx
0x180060d55  push    rsi
0x180060d56  push    rdi
0x180060d57  push    r14
0x180060d59  sub     rsp, 30h
0x180060d5d  mov     r14, r8
0x180060d60  mov     rsi, rcx
0x180060d63  cmp     edx, 9
0x180060d66  jg      loc_180060F50
0x180060d6c  jz      loc_180060F46
0x180060d72  xor     edi, edi
0x180060d74  test    edx, edx
0x180060d76  jz      loc_180060F38
0x180060d7c  sub     edx, 1
0x180060d7f  jz      loc_180060F29
0x180060d85  sub     edx, 1
0x180060d88  jz      loc_180060EB5
0x180060d8e  sub     edx, 1
0x180060d91  jz      loc_180060EA0
0x180060d97  sub     edx, 1
0x180060d9a  jz      loc_180060E8F
0x180060da0  sub     edx, 1
0x180060da3  jz      loc_180060E82
0x180060da9  sub     edx, 1
0x180060dac  jz      loc_180060E78
0x180060db2  sub     edx, 1
0x180060db5  jz      short loc_180060DD3
0x180060db7  cmp     edx, 1
0x180060dba  jnz     loc_1800610B1
0x180060dc0  or      r8d, 0FFFFFFFFh
0x180060dc4  mov     edx, 3
0x180060dc9  call    AgCxKnownContextStartPhase
0x180060dce  jmp     loc_180061133
0x180060dd3  call    cs:__imp_GetCurrentThread
0x180060dd9  mov     r9d, 4; ThreadInformationLength
0x180060ddf  mov     [rsp+48h+ThreadInformation], edi
0x180060de3  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x180060de8  mov     [rsp+48h+ReturnLength], rdi; ReturnLength
0x180060ded  mov     rcx, rax; ThreadHandle
0x180060df0  lea     edx, [r9+12h]; ThreadInformationClass
0x180060df4  call    cs:__imp_NtQueryInformationThread
0x180060dfa  test    eax, eax
0x180060dfc  jns     short loc_180060E0D
0x180060dfe  mov     ecx, eax; Status
0x180060e00  call    cs:__imp_RtlNtStatusToDosError
0x180060e06  mov     ebx, 5
0x180060e0b  jmp     short loc_180060E11
0x180060e0d  mov     ebx, [rsp+48h+ThreadInformation]
0x180060e11  call    cs:__imp_GetCurrentThread
0x180060e17  mov     rcx, rax; ThreadHandle
0x180060e1a  xor     edx, edx
0x180060e1c  call    PfSetIoPriorityThread
0x180060e21  call    AgCxFilesCleanup
0x180060e26  mov     edi, eax
0x180060e28  cmp     ebx, 5
0x180060e2b  jz      short loc_180060E3D
0x180060e2d  call    cs:__imp_GetCurrentThread
0x180060e33  mov     rcx, rax; ThreadHandle
0x180060e36  mov     edx, ebx
0x180060e38  call    PfSetIoPriorityThread
0x180060e3d  mov     r10, cs:PfSvcGlobals
0x180060e44  call    PfsActionItemGetCurrentTime
0x180060e49  xor     r9d, r9d
0x180060e4c  lea     r8, [rsp+48h+arg_18]
0x180060e51  mov     rcx, 0C92A69C000h
0x180060e5b  add     rax, rcx
0x180060e5e  lea     rcx, [r10+6B8h]; lpCriticalSection
0x180060e65  mov     [rsp+48h+arg_18], rax
0x180060e6a  lea     edx, [r9+6]
0x180060e6e  call    PfsActionItemQueueEx
0x180060e73  jmp     loc_180061135
0x180060e78  call    AgCxUserDisconnect
0x180060e7d  jmp     loc_180061133
0x180060e82  mov     edx, r14d
0x180060e85  call    AgCxUserConnect
0x180060e8a  jmp     loc_180061133
0x180060e8f  lea     rdx, [rcx+3A40h]
0x180060e96  call    AgCxPrefetchEndCheck
0x180060e9b  jmp     loc_180061135
0x180060ea0  mov     edx, 2
0x180060ea5  mov     r8d, 1
0x180060eab  call    AgCxKnownContextEnd
0x180060eb0  jmp     loc_180061133
0x180060eb5  test    r14d, r14d
0x180060eb8  jz      short loc_180060F1B
0x180060eba  mov     ecx, ds:7FFE0004h
0x180060ec1  lea     rbx, [rsi+0D70h]
0x180060ec8  shl     rcx, 20h
0x180060ecc  mov     eax, 7FFE0320h
0x180060ed1  mov     r9, rbx
0x180060ed4  mov     dword ptr [rsp+48h+ReturnLength], 4
0x180060edc  mov     rax, [rax]
0x180060edf  shl     rax, 8
0x180060ee3  mul     rcx
0x180060ee6  mov     rax, cs:PfSvcGlobals
0x180060eed  mov     rcx, rsi
0x180060ef0  shr     rdx, 0Ah
0x180060ef4  add     edx, [rax+0F0h]
0x180060efa  mov     r8d, edx
0x180060efd  xor     edx, edx
0x180060eff  call    AgCxSnapshotRestore
0x180060f04  mov     rcx, rbx
0x180060f07  mov     edi, eax
0x180060f09  call    BtDbDatabaseCleanup
0x180060f0e  mov     rcx, rbx; void *
0x180060f11  call    PfSpDbInitialize
0x180060f16  jmp     loc_180061135
0x180060f1b  or      r8d, 0FFFFFFFFh
0x180060f1f  mov     edx, 2
0x180060f24  jmp     loc_180060DC9
0x180060f29  mov     edi, 1
0x180060f2e  mov     r8d, edi
0x180060f31  mov     edx, edi
0x180060f33  jmp     loc_180060EAB
0x180060f38  or      r8d, 0FFFFFFFFh
0x180060f3c  mov     edx, 1
0x180060f41  jmp     loc_180060DC9
0x180060f46  mov     edx, 3
0x180060f4b  jmp     loc_180060EA5
0x180060f50  mov     ecx, edx
0x180060f52  sub     ecx, 0Ah
0x180060f55  jz      loc_180061091
0x180060f5b  sub     ecx, 1
0x180060f5e  jz      short loc_180060FDF
0x180060f60  sub     ecx, 1
0x180060f63  jz      short loc_180060FDF
0x180060f65  sub     ecx, 1
0x180060f68  jz      short loc_180060FC6
0x180060f6a  sub     ecx, 1
0x180060f6d  jz      short loc_180060FBC
0x180060f6f  sub     ecx, 1
0x180060f72  jz      short loc_180060FB5
0x180060f74  sub     ecx, 1
0x180060f77  jz      short loc_180060FA4
0x180060f79  sub     ecx, 1
0x180060f7c  jz      short loc_180060F97
0x180060f7e  cmp     ecx, 1
0x180060f81  jnz     loc_1800610B1
0x180060f87  mov     rdx, r14
0x180060f8a  mov     rcx, rsi
0x180060f8d  call    AgCxUserLazyDisconnect
0x180060f92  jmp     loc_180061133
0x180060f97  mov     edx, 5
0x180060f9c  mov     rcx, rsi
0x180060f9f  jmp     loc_180060EA5
0x180060fa4  or      r8d, 0FFFFFFFFh
0x180060fa8  mov     edx, 5
0x180060fad  mov     rcx, rsi
0x180060fb0  jmp     loc_180060DC9
0x180060fb5  mov     edx, 4
0x180060fba  jmp     short loc_180060F9C
0x180060fbc  mov     edx, 4
0x180060fc1  mov     r8d, edx
0x180060fc4  jmp     short loc_180060FAD
0x180060fc6  mov     edx, 4
0x180060fcb  mov     rcx, rsi
0x180060fce  lea     r8d, [rdx-3]
0x180060fd2  call    AgCxKnownContextStartPhase
0x180060fd7  mov     r8d, 2
0x180060fdd  jmp     short loc_180060FA8
0x180060fdf  mov     ecx, [r8]
0x180060fe2  sub     ecx, 1
0x180060fe5  jz      loc_18006107C
0x180060feb  sub     ecx, 1
0x180060fee  jz      short loc_180061052
0x180060ff0  sub     ecx, 1
0x180060ff3  jz      short loc_18006103B
0x180060ff5  sub     ecx, 1
0x180060ff8  jz      short loc_180061029
0x180060ffa  cmp     ecx, 1
0x180060ffd  jnz     loc_1800610B1
0x180061003  mov     rcx, rsi
0x180061006  cmp     edx, 0Ch
0x180061009  jnz     short loc_18006101D
0x18006100b  mov     edx, 11h
0x180061010  xor     r8d, r8d
0x180061013  call    AgCxContextNotify
0x180061018  jmp     loc_180061133
0x18006101d  xor     r8d, r8d
0x180061020  lea     edx, [r8+5]
0x180061024  jmp     loc_180060DC9
0x180061029  sub     edx, 0Ch
0x18006102c  neg     edx
0x18006102e  sbb     edx, edx
0x180061030  add     edx, 0Fh
0x180061033  xor     r8d, r8d
0x180061036  mov     rcx, rsi
0x180061039  jmp     short loc_180061013
0x18006103b  mov     rcx, rsi
0x18006103e  cmp     edx, 0Ch
0x180061041  jnz     short loc_18006104A
0x180061043  mov     edx, 9
0x180061048  jmp     short loc_180061010
0x18006104a  xor     r8d, r8d
0x18006104d  jmp     loc_180060DC4
0x180061052  cmp     edx, 0Ch
0x180061055  jnz     short loc_180061060
0x180061057  mov     edx, 3
0x18006105c  xor     edi, edi
0x18006105e  jmp     short loc_180061077
0x180061060  xor     r8d, r8d
0x180061063  mov     rcx, rsi
0x180061066  lea     edx, [r8+2]
0x18006106a  call    AgCxKnownContextStartPhase
0x18006106f  mov     edx, 2
0x180061074  lea     edi, [rdx-1]
0x180061077  mov     r8, rdi
0x18006107a  jmp     short loc_180061036
0x18006107c  cmp     edx, 0Ch
0x18006107f  mov     rcx, rsi
0x180061082  mov     edx, 1
0x180061087  jz      short loc_180061010
0x180061089  xor     r8d, r8d
0x18006108c  jmp     loc_180060DC9
0x180061091  mov     ecx, [r8]
0x180061094  sub     ecx, 1
0x180061097  jz      loc_180061126
0x18006109d  sub     ecx, 1
0x1800610a0  jz      short loc_1800610F3
0x1800610a2  sub     ecx, 1
0x1800610a5  jz      short loc_1800610EC
0x1800610a7  sub     ecx, 1
0x1800610aa  jz      short loc_1800610BF
0x1800610ac  cmp     ecx, 1
0x1800610af  jz      short loc_1800610B8
0x1800610b1  mov     edi, 54Fh
0x1800610b6  jmp     short loc_180061135
0x1800610b8  mov     edx, 5
0x1800610bd  jmp     short loc_18006112B
0x1800610bf  mov     rax, cs:PfSvcGlobals
0x1800610c6  cmp     dword ptr [rax+750h], 0FFFFFFFFh
0x1800610cd  jz      short loc_1800610D3
0x1800610cf  xor     edi, edi
0x1800610d1  jmp     short loc_180061135
0x1800610d3  mov     edx, 4
0x1800610d8  mov     rcx, rsi
0x1800610db  call    AgCxKnownContextStart
0x1800610e0  xor     r8d, r8d
0x1800610e3  lea     edx, [r8+4]
0x1800610e7  jmp     loc_180060FAD
0x1800610ec  mov     edx, 3
0x1800610f1  jmp     short loc_18006112B
0x1800610f3  lea     rbx, [rsi+0D70h]
0x1800610fa  mov     rcx, rbx
0x1800610fd  call    BtDbDatabaseCleanup
0x180061102  mov     rcx, rbx; void *
0x180061105  call    PfSpDbInitialize
0x18006110a  or      r9d, 0FFFFFFFFh
0x18006110e  xor     r8d, r8d
0x180061111  mov     rdx, rbx
0x180061114  mov     rcx, rsi
0x180061117  call    AgCxSnapshotBuild
0x18006111c  mov     r8, r14
0x18006111f  mov     edx, 2
0x180061124  jmp     short loc_18006112B
0x180061126  mov     edx, 1
0x18006112b  mov     rcx, rsi
0x18006112e  call    AgCxKnownContextStart
0x180061133  mov     edi, eax
0x180061135  mov     rbx, [rsp+48h+arg_0]
0x18006113a  mov     eax, edi
0x18006113c  add     rsp, 30h
0x180061140  pop     r14
0x180061142  pop     rdi
0x180061143  pop     rsi
0x180061144  retn
```
