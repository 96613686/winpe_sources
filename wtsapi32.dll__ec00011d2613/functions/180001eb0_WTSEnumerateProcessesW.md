# WTSEnumerateProcessesW

- ea: `0x180001eb0`
- end: `0x180002225`
- name: `WTSEnumerateProcessesW`
- size: `885`
- prototype: `BOOL __stdcall(HANDLE hServer, DWORD Reserved, DWORD Version, PWTS_PROCESS_INFOW *ppProcessInfo, DWORD *pCount)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b90`

## callees

- `0x180001eb0`
- `0x180015582`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002096`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000212a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000212a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001f59`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002007`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002108`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800021ca`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001f59`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002007`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180002108`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800021ca`
- `WINSTA!WinStationEnumerateProcesses` at `0x1800020ba`
- `WINSTA!WinStationEnumerateProcesses` at `0x1800020ba`
- `WINSTA!WinStationGetAllProcesses` at `0x180001f0e`
- `WINSTA!WinStationGetAllProcesses` at `0x180001f0e`
- `WINSTA!WinStationFreeGAPMemory` at `0x180002044`
- `WINSTA!WinStationFreeGAPMemory` at `0x1800020a8`
- `WINSTA!WinStationFreeGAPMemory` at `0x180002044`
- `WINSTA!WinStationFreeGAPMemory` at `0x1800020a8`
- `WINSTA!WinStationFreeMemory` at `0x18000213c`
- `WINSTA!WinStationFreeMemory` at `0x180002212`
- `WINSTA!WinStationFreeMemory` at `0x18000213c`
- `WINSTA!WinStationFreeMemory` at `0x180002212`

## pseudocode

```c
BOOL __stdcall WTSEnumerateProcessesW(
        HANDLE hServer,
        DWORD Reserved,
        DWORD Version,
        PWTS_PROCESS_INFOW *ppProcessInfo,
        DWORD *pCount)
{
  DWORD *v7; // rsi
  unsigned int v8; // r9d
  DWORD v9; // r8d
  unsigned int i; // ebx
  _QWORD *v11; // rdx
  void *v12; // rcx
  DWORD v13; // edi
  DWORD LengthSid; // eax
  struct _WTS_PROCESS_INFOW *v15; // rax
  struct _WTS_PROCESS_INFOW *v16; // rbx
  __int64 v17; // r8
  unsigned int v18; // r14d
  struct _WTS_PROCESS_INFOW *v19; // r15
  __int64 v20; // r12
  __int64 v21; // rsi
  unsigned int v22; // eax
  __int64 v23; // rdi
  void *v24; // rcx
  DWORD v25; // eax
  __int64 v26; // rdi
  const void **v28; // rbx
  unsigned int v29; // edx
  __int64 v30; // r8
  __int64 v31; // rax
  int v32; // edi
  __int64 v33; // rax
  void *v34; // rcx
  DWORD v35; // eax
  struct _WTS_PROCESS_INFOW *v36; // rax
  struct _WTS_PROCESS_INFOW *v37; // rdi
  __int64 v38; // rdx
  unsigned int v39; // r14d
  const void **v40; // rsi
  struct _WTS_PROCESS_INFOW *v41; // r15
  __int64 v42; // rax
  unsigned int v43; // eax
  __int64 v44; // rbx
  char *v45; // r13
  void *v46; // rcx
  DWORD v47; // eax
  __int64 v48; // rbx
  __int64 v49; // [rsp+20h] [rbp-10h] BYREF
  const void **v50; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v51; // [rsp+68h] [rbp+38h] BYREF

  v50 = 0;
  v51 = 0;
  v49 = 0;
  if ( Reserved || Version != 1 || !ppProcessInfo )
  {
    v7 = pCount;
    goto LABEL_24;
  }
  v7 = pCount;
  if ( !pCount )
  {
LABEL_24:
    SetLastError(0x57u);
    goto LABEL_19;
  }
  if ( (unsigned __int8)WinStationGetAllProcesses(hServer, Reserved, &v51, &v49) )
  {
    v8 = v51;
    v9 = 0;
    for ( i = 0; i < v8; ++i )
    {
      v11 = (_QWORD *)(v49 + 24LL * i);
      v12 = (void *)v11[2];
      v13 = v9 + *(unsigned __int16 *)(*v11 + 56LL) + 2;
      if ( v12 )
      {
        LengthSid = GetLengthSid(v12);
        v8 = v51;
        v9 = v13 + LengthSid;
      }
      else
      {
        v9 += *(unsigned __int16 *)(*v11 + 56LL) + 2;
      }
    }
    v15 = (struct _WTS_PROCESS_INFOW *)LocalAlloc(0x40u, v9 + 24LL * v8);
    v16 = v15;
    if ( v15 )
    {
      v17 = v51;
      *ppProcessInfo = v15;
      v18 = 0;
      *v7 = v17;
      v19 = &v15[v17];
      if ( (_DWORD)v17 )
      {
        do
        {
          v20 = 24LL * v18;
          v21 = *(_QWORD *)(v20 + v49);
          v22 = *(unsigned __int16 *)(v21 + 56);
          v16->pProcessName = (LPWSTR)v19;
          v23 = v22;
          memcpy_0(v19, *(const void **)(v21 + 64), v22);
          *((_BYTE *)&v19->SessionId + v23) = 0;
          v19 = (struct _WTS_PROCESS_INFOW *)((char *)v19 + v23 + 2);
          v16->ProcessId = *(_DWORD *)(v21 + 76);
          v16->SessionId = *(_DWORD *)(v21 + 88);
          v24 = *(void **)(v20 + v49 + 16);
          if ( v24 )
          {
            v25 = GetLengthSid(v24);
            v16->pUserSid = v19;
            v26 = v25;
            memcpy_0(v19, *(const void **)(v20 + v49 + 16), v25);
            v19 = (struct _WTS_PROCESS_INFOW *)((char *)v19 + v26);
          }
          v17 = v51;
          ++v16;
          ++v18;
        }
        while ( v18 < v51 );
      }
      WinStationFreeGAPMemory(0, v49, v17);
      return 1;
    }
    WinStationFreeGAPMemory(0, v49, v51);
    goto LABEL_26;
  }
  if ( GetLastError() == 1745 && (unsigned __int8)WinStationEnumerateProcesses(hServer, &v50) )
  {
    v28 = v50;
    v29 = 0;
    LODWORD(v30) = 0;
    v31 = 0;
    do
    {
      v28 = (const void **)((char *)v28 + v31);
      v51 = ++v29;
      v30 = *((unsigned __int16 *)v28 + 28) + 2 + (unsigned int)v30;
      v32 = v30;
      v33 = (int)(*((_DWORD *)v28 + 1) << 6);
      if ( *(_DWORD *)((char *)v28 + v33 + 136) == 592008274 )
      {
        v34 = *(void **)((char *)v28 + v33 + 144);
        if ( v34 )
        {
          v35 = GetLengthSid(v34);
          v29 = v51;
          v30 = v32 + v35;
        }
      }
      v31 = *(unsigned int *)v28;
    }
    while ( (_DWORD)v31 );
    v36 = (struct _WTS_PROCESS_INFOW *)LocalAlloc(0x40u, v30 + 24LL * v29);
    v37 = v36;
    if ( v36 )
    {
      v38 = v51;
      *ppProcessInfo = v36;
      v39 = 0;
      *v7 = v38;
      v40 = v50;
      v41 = &v36[v38];
      v42 = 0;
      if ( (_DWORD)v38 )
      {
        do
        {
          v40 = (const void **)((char *)v40 + v42);
          v43 = *((unsigned __int16 *)v40 + 28);
          v37->pProcessName = (LPWSTR)v41;
          v44 = v43;
          memcpy_0(v41, v40[8], v43);
          *((_BYTE *)&v41->SessionId + v44) = 0;
          v41 = (struct _WTS_PROCESS_INFOW *)((char *)v41 + v44 + 2);
          v37->ProcessId = *((_DWORD *)v40 + 19);
          v45 = (char *)v40 + (int)(*((_DWORD *)v40 + 1) << 6);
          if ( *((_DWORD *)v45 + 34) == 592008274 )
          {
            v37->SessionId = *((_DWORD *)v45 + 35);
            v46 = (void *)*((_QWORD *)v45 + 18);
            if ( v46 )
            {
              v47 = GetLengthSid(v46);
              v37->pUserSid = v41;
              v48 = v47;
              memcpy_0(v41, *((const void **)v45 + 18), v47);
              v41 = (struct _WTS_PROCESS_INFOW *)((char *)v41 + v48);
            }
          }
          else
          {
            v37->SessionId = -1;
          }
          v42 = *(unsigned int *)v40;
          ++v37;
          ++v39;
        }
        while ( v39 < v51 );
        v40 = v50;
      }
      WinStationFreeMemory(v40);
      return 1;
    }
    WinStationFreeMemory(v50);
  }
LABEL_19:
  if ( ppProcessInfo )
LABEL_26:
    *ppProcessInfo = 0;
  if ( v7 )
    *v7 = 0;
  return 0;
}

```

## disassembly

```asm
0x180001eb0  mov     [rsp-28h+arg_10], rbx
0x180001eb5  mov     [rsp-28h+arg_18], rsi
0x180001eba  push    rbp
0x180001ebb  push    rdi
0x180001ebc  push    r12
0x180001ebe  push    r14
0x180001ec0  push    r15
0x180001ec2  mov     rbp, rsp
0x180001ec5  sub     rsp, 30h
0x180001ec9  xor     r12d, r12d
0x180001ecc  mov     r14, r9
0x180001ecf  mov     [rbp+var_8], r12
0x180001ed3  mov     rbx, rcx
0x180001ed6  mov     [rbp+arg_8], r12d
0x180001eda  mov     [rbp+var_10], r12
0x180001ede  test    edx, edx
0x180001ee0  jnz     loc_18000208D
0x180001ee6  cmp     r8d, 1
0x180001eea  jnz     loc_18000208D
0x180001ef0  test    r9, r9
0x180001ef3  jz      loc_18000208D
0x180001ef9  mov     rsi, [rbp+pCount]
0x180001efd  test    rsi, rsi
0x180001f00  jz      loc_180002091
0x180001f06  lea     r9, [rbp+var_10]
0x180001f0a  lea     r8, [rbp+arg_8]
0x180001f0e  call    cs:__imp_WinStationGetAllProcesses
0x180001f14  test    al, al
0x180001f16  jz      loc_18000206E
0x180001f1c  mov     r9d, [rbp+arg_8]
0x180001f20  mov     r8d, r12d
0x180001f23  mov     ebx, r12d
0x180001f26  test    r9d, r9d
0x180001f29  jz      short loc_180001F6E
0x180001f2b  nop     dword ptr [rax+rax+00h]
0x180001f30  mov     eax, ebx
0x180001f32  lea     rcx, [rax+rax*2]
0x180001f36  mov     rax, [rbp+var_10]
0x180001f3a  lea     rdx, [rax+rcx*8]
0x180001f3e  mov     rax, [rax+rcx*8]
0x180001f42  mov     rcx, [rdx+10h]; pSid
0x180001f46  movzx   edi, word ptr [rax+38h]
0x180001f4a  add     edi, 2
0x180001f4d  add     edi, r8d
0x180001f50  test    rcx, rcx
0x180001f53  jz      loc_180002066
0x180001f59  call    cs:__imp_GetLengthSid
0x180001f5f  mov     r9d, [rbp+arg_8]
0x180001f63  lea     r8d, [rdi+rax]
0x180001f67  inc     ebx
0x180001f69  cmp     ebx, r9d
0x180001f6c  jb      short loc_180001F30
0x180001f6e  mov     eax, r9d
0x180001f71  lea     rcx, [rax+rax*2]
0x180001f75  mov     eax, r8d
0x180001f78  lea     rdx, [rax+rcx*8]; uBytes
0x180001f7c  mov     ecx, 40h ; '@'; uFlags
0x180001f81  call    cs:__imp_LocalAlloc
0x180001f87  mov     rbx, rax
0x180001f8a  test    rax, rax
0x180001f8d  jz      loc_18000209E
0x180001f93  mov     r8d, [rbp+arg_8]
0x180001f97  mov     [r14], rax
0x180001f9a  mov     r14d, r12d
0x180001f9d  mov     [rsi], r8d
0x180001fa0  lea     rcx, [r8+r8*2]
0x180001fa4  lea     r15, [rax+rcx*8]
0x180001fa8  test    r8d, r8d
0x180001fab  jz      loc_18000203E
0x180001fb1  mov     eax, r14d
0x180001fb4  lea     rcx, [rax+rax*2]
0x180001fb8  mov     rax, [rbp+var_10]
0x180001fbc  lea     r12, ds:0[rcx*8]
0x180001fc4  mov     rcx, r15; void *
0x180001fc7  mov     rsi, [r12+rax]
0x180001fcb  movzx   eax, word ptr [rsi+38h]
0x180001fcf  mov     [rbx+8], r15
0x180001fd3  mov     r8d, eax; Size
0x180001fd6  mov     rdx, [rsi+40h]; Src
0x180001fda  mov     edi, eax
0x180001fdc  call    memcpy_0
0x180001fe1  mov     byte ptr [rdi+r15], 0
0x180001fe6  lea     rax, [rdi+r15]
0x180001fea  lea     r15, [rax+2]
0x180001fee  mov     eax, [rsi+4Ch]
0x180001ff1  mov     [rbx+4], eax
0x180001ff4  mov     eax, [rsi+58h]
0x180001ff7  mov     [rbx], eax
0x180001ff9  mov     rax, [rbp+var_10]
0x180001ffd  mov     rcx, [r12+rax+10h]; pSid
0x180002002  test    rcx, rcx
0x180002005  jz      short loc_18000202A
0x180002007  call    cs:__imp_GetLengthSid
0x18000200d  mov     [rbx+10h], r15
0x180002011  mov     rcx, r15; void *
0x180002014  mov     rdx, [rbp+var_10]
0x180002018  mov     r8d, eax; Size
0x18000201b  mov     edi, eax
0x18000201d  mov     rdx, [r12+rdx+10h]; Src
0x180002022  call    memcpy_0
0x180002027  add     r15, rdi
0x18000202a  mov     r8d, [rbp+arg_8]
0x18000202e  add     rbx, 18h
0x180002032  inc     r14d
0x180002035  cmp     r14d, r8d
0x180002038  jb      loc_180001FB1
0x18000203e  mov     rdx, [rbp+var_10]
0x180002042  xor     ecx, ecx
0x180002044  call    cs:__imp_WinStationFreeGAPMemory
0x18000204a  mov     eax, 1
0x18000204f  mov     rbx, [rsp+30h+arg_10]
0x180002054  mov     rsi, [rsp+30h+arg_18]
0x180002059  add     rsp, 30h
0x18000205d  pop     r15
0x18000205f  pop     r14
0x180002061  pop     r12
0x180002063  pop     rdi
0x180002064  pop     rbp
0x180002065  retn
0x180002066  mov     r8d, edi
0x180002069  jmp     loc_180001F67
0x18000206e  call    cs:__imp_GetLastError
0x180002074  cmp     eax, 6D1h
0x180002079  jz      short loc_1800020B3
0x18000207b  test    r14, r14
0x18000207e  jnz     short loc_1800020AE
0x180002080  test    rsi, rsi
0x180002083  jnz     loc_18000221D
0x180002089  xor     eax, eax
0x18000208b  jmp     short loc_18000204F
0x18000208d  mov     rsi, [rbp+pCount]
0x180002091  mov     ecx, 57h ; 'W'; dwErrCode
0x180002096  call    cs:__imp_SetLastError
0x18000209c  jmp     short loc_18000207B
0x18000209e  mov     r8d, [rbp+arg_8]
0x1800020a2  xor     ecx, ecx
0x1800020a4  mov     rdx, [rbp+var_10]
0x1800020a8  call    cs:__imp_WinStationFreeGAPMemory
0x1800020ae  mov     [r14], r12
0x1800020b1  jmp     short loc_180002080
0x1800020b3  lea     rdx, [rbp+var_8]
0x1800020b7  mov     rcx, rbx
0x1800020ba  call    cs:__imp_WinStationEnumerateProcesses
0x1800020c0  test    al, al
0x1800020c2  jz      short loc_18000207B
0x1800020c4  mov     rbx, [rbp+var_8]
0x1800020c8  mov     edx, r12d
0x1800020cb  mov     r8d, r12d
0x1800020ce  mov     eax, r12d
0x1800020d1  add     rbx, rax
0x1800020d4  inc     edx
0x1800020d6  mov     [rbp+arg_8], edx
0x1800020d9  movzx   eax, word ptr [rbx+38h]
0x1800020dd  add     eax, 2
0x1800020e0  add     r8d, eax
0x1800020e3  mov     eax, [rbx+4]
0x1800020e6  shl     eax, 6
0x1800020e9  mov     edi, r8d
0x1800020ec  cdqe
0x1800020ee  cmp     dword ptr [rax+rbx+88h], 23495452h
0x1800020f9  jnz     short loc_180002115
0x1800020fb  mov     rcx, [rax+rbx+90h]; pSid
0x180002103  test    rcx, rcx
0x180002106  jz      short loc_180002115
0x180002108  call    cs:__imp_GetLengthSid
0x18000210e  mov     edx, [rbp+arg_8]
0x180002111  lea     r8d, [rdi+rax]
0x180002115  mov     eax, [rbx]
0x180002117  test    eax, eax
0x180002119  jnz     short loc_1800020D1
0x18000211b  mov     ecx, edx
0x18000211d  lea     rdx, [rcx+rcx*2]
0x180002121  mov     ecx, 40h ; '@'; uFlags
0x180002126  lea     rdx, [r8+rdx*8]; uBytes
0x18000212a  call    cs:__imp_LocalAlloc
0x180002130  mov     rdi, rax
0x180002133  test    rax, rax
0x180002136  jnz     short loc_180002147
0x180002138  mov     rcx, [rbp+var_8]
0x18000213c  call    cs:__imp_WinStationFreeMemory
0x180002142  jmp     loc_18000207B
0x180002147  mov     edx, [rbp+arg_8]
0x18000214a  mov     [r14], rax
0x18000214d  mov     r14d, r12d
0x180002150  mov     [rsi], edx
0x180002152  mov     rsi, [rbp+var_8]
0x180002156  lea     rcx, [rdx+rdx*2]
0x18000215a  lea     r15, [rax+rcx*8]
0x18000215e  mov     eax, r12d
0x180002161  test    edx, edx
0x180002163  jz      loc_18000220F
0x180002169  mov     [rsp+30h+arg_0], r13
0x18000216e  add     rsi, rax
0x180002171  mov     rcx, r15; void *
0x180002174  movzx   eax, word ptr [rsi+38h]
0x180002178  mov     [rdi+8], r15
0x18000217c  mov     r8d, eax; Size
0x18000217f  mov     rdx, [rsi+40h]; Src
0x180002183  mov     ebx, eax
0x180002185  call    memcpy_0
0x18000218a  mov     [rbx+r15], r12b
0x18000218e  lea     rax, [rbx+r15]
0x180002192  lea     r15, [rax+2]
0x180002196  mov     eax, [rsi+4Ch]
0x180002199  mov     [rdi+4], eax
0x18000219c  mov     eax, [rsi+4]
0x18000219f  shl     eax, 6
0x1800021a2  movsxd  r13, eax
0x1800021a5  add     r13, rsi
0x1800021a8  cmp     dword ptr [r13+88h], 23495452h
0x1800021b3  jnz     short loc_1800021ED
0x1800021b5  mov     eax, [r13+8Ch]
0x1800021bc  mov     [rdi], eax
0x1800021be  mov     rcx, [r13+90h]; pSid
0x1800021c5  test    rcx, rcx
0x1800021c8  jz      short loc_1800021F3
0x1800021ca  call    cs:__imp_GetLengthSid
0x1800021d0  mov     [rdi+10h], r15
0x1800021d4  mov     rcx, r15; void *
0x1800021d7  mov     rdx, [r13+90h]; Src
0x1800021de  mov     r8d, eax; Size
0x1800021e1  mov     ebx, eax
0x1800021e3  call    memcpy_0
0x1800021e8  add     r15, rbx
0x1800021eb  jmp     short loc_1800021F3
0x1800021ed  mov     dword ptr [rdi], 0FFFFFFFFh
0x1800021f3  mov     eax, [rsi]
0x1800021f5  add     rdi, 18h
0x1800021f9  inc     r14d
0x1800021fc  cmp     r14d, [rbp+arg_8]
0x180002200  jb      loc_18000216E
0x180002206  mov     r13, [rsp+30h+arg_0]
0x18000220b  mov     rsi, [rbp+var_8]
0x18000220f  mov     rcx, rsi
0x180002212  call    cs:__imp_WinStationFreeMemory
0x180002218  jmp     loc_18000204A
0x18000221d  mov     [rsi], r12d
0x180002220  jmp     loc_180002089
```
