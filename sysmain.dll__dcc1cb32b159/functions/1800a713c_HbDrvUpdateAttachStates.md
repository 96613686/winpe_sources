# HbDrvUpdateAttachStates

- ea: `0x1800a713c`
- end: `0x1800a75c4`
- name: `HbDrvUpdateAttachStates`
- size: `1160`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a6088`
- `0x1800a6758`

## callees

- `0x1800076c4`
- `0x18003bafc`
- `0x180057444`
- `0x18005cb4c`
- `0x18005d61c`
- `0x180060890`
- `0x1800613e8`
- `0x180073e08`
- `0x1800a713c`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtClose` at `0x1800a72db`
- `ntdll!NtClose` at `0x1800a7558`
- `ntdll!NtClose` at `0x1800a72db`
- `ntdll!NtClose` at `0x1800a7558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a72fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7474`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7540`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7573`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a72fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7474`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7540`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a7573`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a74ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a74ad`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800a73db`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800a73db`
- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSendCommand` at `0x1800a7516`
- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSendCommand` at `0x1800a7516`

## pseudocode

```c
__int64 __fastcall HbDrvUpdateAttachStates(_QWORD *a1, __int64 a2, unsigned int a3, int a4, int a5)
{
  __int64 v5; // r12
  _QWORD *v6; // r15
  _DWORD *v7; // r14
  void *v8; // rsi
  wchar_t *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned int v13; // ecx
  __int64 v14; // r13
  __int64 v15; // rbx
  __int64 v16; // rsi
  _DWORD *v17; // rdx
  HANDLE v18; // rcx
  int v19; // r15d
  unsigned int UniqueId; // eax
  unsigned int v21; // ebx
  int v22; // r12d
  REGHANDLE v23; // rcx
  __int64 v24; // rsi
  void *v25; // rcx
  _DWORD *v26; // rax
  unsigned int v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD Size[3]; // [rsp+4Ch] [rbp-B4h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v33; // [rsp+68h] [rbp-98h]
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  unsigned int v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+7Ch] [rbp-84h]
  HANDLE hDevice; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[528]; // [rsp+A0h] [rbp-60h] BYREF

  v38 = a2;
  v5 = a2;
  v33 = a1;
  v6 = a1;
  memset(Size, 0, sizeof(Size));
  v28 = 0;
  v29 = 0;
  v7 = 0;
  v8 = 0;
  hDevice = 0;
  v9 = 0;
  lpMem = 0;
  v32 = 0;
  v36 = a4;
  v35 = a3;
  v10 = PfsAttachStateCtxStart(&v32, 0);
  if ( v10 )
    goto LABEL_53;
  v12 = 0;
  while ( 2 )
  {
    v31 = v12;
    if ( (unsigned int)v12 < *((_DWORD *)v6 + 2) )
    {
      v13 = 0;
      v14 = 6 * v12;
      while ( 1 )
      {
        v15 = v13;
        if ( v13 >= v35 )
          break;
        v11 = *v6;
        v16 = 48LL * v13;
        v17 = *(_DWORD **)(v16 + v5 + 8);
        if ( v17[2] == *(_DWORD *)(*v6 + 48 * v12 + 8)
          && v17[1] == *(_DWORD *)(v11 + 48 * v12 + 4)
          && *v17 == *(_DWORD *)(v11 + 48 * v12) )
        {
          v18 = *(HANDLE *)(v16 + v5 + 16);
          v19 = 1;
          hDevice = v18;
          goto LABEL_13;
        }
        ++v13;
      }
      if ( (unsigned int)HbDrvGetVolumeHandle(*(_QWORD *)(*v6 + 48 * v12 + 16), &hDevice, v11, 1) )
      {
        v8 = *(void **)&Size[1];
LABEL_24:
        v12 = (unsigned int)(v31 + 1);
        continue;
      }
      v18 = hDevice;
      v19 = 0;
      *(_QWORD *)&Size[1] = hDevice;
      v16 = 48 * v15;
LABEL_13:
      UniqueId = PfsVolumeQueryUniqueId(v18);
      v9 = (wchar_t *)lpMem;
      v10 = UniqueId;
      if ( UniqueId )
        goto LABEL_50;
      v21 = 0;
      v22 = 0;
      if ( !v19 )
      {
        if ( !(unsigned int)PfsGetAttachState((unsigned int)&v32, (_DWORD)lpMem, (unsigned int)&v28, 1, (__int64)&v29)
          && !v28
          && !v29 )
        {
          goto LABEL_18;
        }
        goto LABEL_41;
      }
      v22 = (*(_DWORD *)(v38 + v16 + 36) & 1) != 0;
      if ( v36 == 1 )
      {
        v21 = 1;
        goto LABEL_41;
      }
      if ( v36 != 2 )
      {
        if ( v36 == 3 )
        {
          v21 = 3;
          goto LABEL_41;
        }
        if ( v36 == 4 )
        {
          if ( (*(_DWORD *)(v38 + v16 + 36) & 1) != 0 )
          {
            v28 = *(_DWORD *)(v38 + v16 + 24);
            if ( *(_QWORD *)&PfSvcGlobals )
            {
              v23 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 472LL);
              if ( v23 )
              {
                *(_QWORD *)&UserData.Size = 4;
                UserData.Ptr = (ULONGLONG)&v28;
                EventWrite(v23, &HBDRV_EVENT_DISABLED_PERFORMANCE, 1u, &UserData);
              }
            }
          }
          v21 = 4;
          goto LABEL_41;
        }
        if ( !(unsigned int)PfsGetAttachState((unsigned int)&v32, (_DWORD)lpMem, (unsigned int)&v28, 1, (__int64)&v29) )
        {
          v21 = v28;
          if ( v28 )
          {
            if ( v29 == v22 )
              goto LABEL_18;
            goto LABEL_42;
          }
        }
      }
      v21 = 2;
LABEL_41:
      v28 = v21;
LABEL_42:
      if ( !a5 )
      {
        v6 = v33;
        PfScStringCopy(*(_QWORD *)&PfSvcGlobals + 96LL, *(_QWORD *)(*v33 + 8 * v14 + 16), v40, 260);
        PfsUpdateAttachState(&v32, v9, v40, v21, 1, v22, 1, 0);
        goto LABEL_19;
      }
      if ( v7 )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
      v24 = -1;
      do
        ++v24;
      while ( v9[v24] );
      v25 = *(void **)(*(_QWORD *)&PfSvcGlobals + 88LL);
      Size[0] = 2 * (unsigned __int16)v24 + 40;
      v26 = HeapAlloc(v25, 0, Size[0]);
      v7 = v26;
      if ( !v26 )
      {
        v10 = 8;
        goto LABEL_50;
      }
      memset_0(v26, 0, Size[0]);
      *(_QWORD *)(v7 + 3) = 0;
      v7[5] = 0;
      v7[1] = 0x8000;
      *v7 = 1;
      v7[2] = 6;
      v7[6] = 1;
      v7[7] = v21;
      *((_WORD *)v7 + 16) = v24;
      StringCbCopyW((STRSAFE_LPWSTR)v7 + 17, 2LL * ((unsigned int)(unsigned __int16)v24 + 1), v9);
      v10 = PfRpcSendCommand(v7, Size);
      if ( v10 )
      {
LABEL_50:
        v8 = *(void **)&Size[1];
        goto LABEL_51;
      }
LABEL_18:
      v6 = v33;
LABEL_19:
      v8 = *(void **)&Size[1];
      if ( *(_QWORD *)&Size[1] )
      {
        NtClose(*(HANDLE *)&Size[1]);
        v8 = 0;
        *(_QWORD *)&Size[1] = 0;
      }
      if ( v9 )
      {
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v9);
        v9 = 0;
        lpMem = 0;
      }
      v5 = v38;
      goto LABEL_24;
    }
    break;
  }
  v10 = 0;
LABEL_51:
  if ( v9 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v9);
LABEL_53:
  PfsAttachStateCtxCleanup(&v32);
  if ( v8 )
    NtClose(v8);
  if ( v7 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
  return v10;
}

```

## disassembly

```asm
0x1800a713c  mov     [rsp-8+arg_10], rbx
0x1800a7141  push    rbp
0x1800a7142  push    rsi
0x1800a7143  push    rdi
0x1800a7144  push    r12
0x1800a7146  push    r13
0x1800a7148  push    r14
0x1800a714a  push    r15
0x1800a714c  lea     rbp, [rsp-1C0h]
0x1800a7154  sub     rsp, 2C0h
0x1800a715b  mov     rax, cs:__security_cookie
0x1800a7162  xor     rax, rsp
0x1800a7165  mov     [rbp+1F0h+var_40], rax
0x1800a716c  xor     r13d, r13d
0x1800a716f  mov     [rbp+1F0h+var_268], rdx
0x1800a7173  mov     r12, rdx
0x1800a7176  mov     [rsp+2F0h+var_288], rcx
0x1800a717b  mov     r15, rcx
0x1800a717e  mov     dword ptr [rsp+2F0h+Size], r13d
0x1800a7183  xor     edx, edx
0x1800a7185  mov     [rsp+2F0h+var_2B0], r13d
0x1800a718a  lea     rcx, [rsp+2F0h+var_290]
0x1800a718f  mov     [rsp+2F0h+var_2A8], r13d
0x1800a7194  mov     r14d, r13d
0x1800a7197  mov     qword ptr [rsp+2F0h+Size+4], r13
0x1800a719c  mov     esi, r13d
0x1800a719f  mov     [rbp+1F0h+hDevice], r13
0x1800a71a3  mov     edi, r13d
0x1800a71a6  mov     [rsp+2F0h+lpMem], r13
0x1800a71ab  mov     [rsp+2F0h+var_290], r13
0x1800a71b0  mov     [rsp+2F0h+var_274], r9d
0x1800a71b5  mov     [rsp+2F0h+var_278], r8d
0x1800a71ba  call    PfsAttachStateCtxStart
0x1800a71bf  mov     ebx, eax
0x1800a71c1  test    eax, eax
0x1800a71c3  jnz     loc_1800A7546
0x1800a71c9  mov     eax, r13d
0x1800a71cc  lea     r9d, [r13+1]
0x1800a71d0  mov     [rsp+2F0h+var_298], eax
0x1800a71d4  cmp     eax, [r15+8]
0x1800a71d8  jnb     loc_1800A75BC
0x1800a71de  mov     ecx, r13d
0x1800a71e1  lea     r13, [rax+rax*2]
0x1800a71e5  add     r13, r13
0x1800a71e8  mov     ebx, ecx
0x1800a71ea  cmp     ecx, [rsp+2F0h+var_278]
0x1800a71ee  jnb     short loc_1800A722F
0x1800a71f0  mov     r8, [r15]
0x1800a71f3  lea     rsi, [rbx+rbx*2]
0x1800a71f7  shl     rsi, 4
0x1800a71fb  mov     eax, [r8+r13*8+8]
0x1800a7200  mov     rdx, [rsi+r12+8]
0x1800a7205  cmp     [rdx+8], eax
0x1800a7208  jnz     short loc_1800A721C
0x1800a720a  mov     eax, [r8+r13*8+4]
0x1800a720f  cmp     [rdx+4], eax
0x1800a7212  jnz     short loc_1800A721C
0x1800a7214  mov     eax, [r8+r13*8]
0x1800a7218  cmp     [rdx], eax
0x1800a721a  jz      short loc_1800A7221
0x1800a721c  add     ecx, r9d
0x1800a721f  jmp     short loc_1800A71E8
0x1800a7221  mov     rcx, [rsi+r12+10h]
0x1800a7226  mov     r15d, r9d
0x1800a7229  mov     [rbp+1F0h+hDevice], rcx
0x1800a722d  jmp     short loc_1800A7260
0x1800a722f  mov     rcx, [r15]
0x1800a7232  lea     rdx, [rbp+1F0h+hDevice]
0x1800a7236  mov     rcx, [rcx+r13*8+10h]
0x1800a723b  call    HbDrvGetVolumeHandle
0x1800a7240  test    eax, eax
0x1800a7242  jnz     loc_1800A75A5
0x1800a7248  mov     rcx, [rbp+1F0h+hDevice]; hDevice
0x1800a724c  lea     rsi, [rbx+rbx*2]
0x1800a7250  xor     r15d, r15d
0x1800a7253  mov     qword ptr [rsp+2F0h+Size+4], rcx
0x1800a7258  shl     rsi, 4
0x1800a725c  lea     r9d, [rax+1]
0x1800a7260  mov     r8d, r9d
0x1800a7263  lea     rdx, [rsp+2F0h+lpMem]
0x1800a7268  call    PfsVolumeQueryUniqueId
0x1800a726d  mov     rdi, [rsp+2F0h+lpMem]
0x1800a7272  mov     ebx, eax
0x1800a7274  test    eax, eax
0x1800a7276  jnz     loc_1800A7526
0x1800a727c  xor     ebx, ebx
0x1800a727e  mov     r12d, ebx
0x1800a7281  test    r15d, r15d
0x1800a7284  jnz     loc_1800A7322
0x1800a728a  lea     rax, [rsp+2F0h+var_2A8]
0x1800a728f  mov     rdx, rdi
0x1800a7292  lea     r9d, [rbx+1]
0x1800a7296  mov     [rsp+2F0h+var_2D0], rax
0x1800a729b  lea     r8, [rsp+2F0h+var_2B0]
0x1800a72a0  lea     rcx, [rsp+2F0h+var_290]
0x1800a72a5  call    PfsGetAttachState
0x1800a72aa  test    eax, eax
0x1800a72ac  jnz     loc_1800A73F2
0x1800a72b2  cmp     [rsp+2F0h+var_2B0], ebx
0x1800a72b6  jnz     loc_1800A73F2
0x1800a72bc  cmp     [rsp+2F0h+var_2A8], ebx
0x1800a72c0  jnz     loc_1800A73F2
0x1800a72c6  xor     r13d, r13d
0x1800a72c9  mov     r15, [rsp+2F0h+var_288]
0x1800a72ce  mov     rsi, qword ptr [rsp+2F0h+Size+4]
0x1800a72d3  test    rsi, rsi
0x1800a72d6  jz      short loc_1800A72E9
0x1800a72d8  mov     rcx, rsi; Handle
0x1800a72db  call    cs:__imp_NtClose
0x1800a72e1  mov     rsi, r13
0x1800a72e4  mov     qword ptr [rsp+2F0h+Size+4], r13
0x1800a72e9  test    rdi, rdi
0x1800a72ec  jz      short loc_1800A730C
0x1800a72ee  mov     rcx, cs:PfSvcGlobals
0x1800a72f5  mov     r8, rdi; lpMem
0x1800a72f8  xor     edx, edx; dwFlags
0x1800a72fa  mov     rcx, [rcx+58h]; hHeap
0x1800a72fe  call    cs:__imp_HeapFree
0x1800a7304  mov     rdi, r13
0x1800a7307  mov     [rsp+2F0h+lpMem], r13
0x1800a730c  mov     r12, [rbp+1F0h+var_268]
0x1800a7310  mov     eax, [rsp+2F0h+var_298]
0x1800a7314  mov     r9d, 1
0x1800a731a  add     eax, r9d
0x1800a731d  jmp     loc_1800A71D0
0x1800a7322  mov     r8, [rbp+1F0h+var_268]
0x1800a7326  mov     r10d, 1
0x1800a732c  mov     ecx, [rsp+2F0h+var_274]
0x1800a7330  mov     edx, [r8+rsi+24h]
0x1800a7335  and     edx, r10d
0x1800a7338  cmovnz  r12d, r10d
0x1800a733c  sub     ecx, r10d
0x1800a733f  jz      loc_1800A73EF
0x1800a7345  sub     ecx, r10d
0x1800a7348  jz      short loc_1800A7390
0x1800a734a  sub     ecx, r10d
0x1800a734d  jz      loc_1800A73E8
0x1800a7353  cmp     ecx, r10d
0x1800a7356  jz      short loc_1800A7397
0x1800a7358  lea     rax, [rsp+2F0h+var_2A8]
0x1800a735d  mov     r9d, r10d
0x1800a7360  lea     r8, [rsp+2F0h+var_2B0]
0x1800a7365  mov     [rsp+2F0h+var_2D0], rax
0x1800a736a  mov     rdx, rdi
0x1800a736d  lea     rcx, [rsp+2F0h+var_290]
0x1800a7372  call    PfsGetAttachState
0x1800a7377  test    eax, eax
0x1800a7379  jnz     short loc_1800A7390
0x1800a737b  mov     ebx, [rsp+2F0h+var_2B0]
0x1800a737f  test    ebx, ebx
0x1800a7381  jz      short loc_1800A7390
0x1800a7383  cmp     [rsp+2F0h+var_2A8], r12d
0x1800a7388  jz      loc_1800A72C6
0x1800a738e  jmp     short loc_1800A73F6
0x1800a7390  mov     ebx, 2
0x1800a7395  jmp     short loc_1800A73F2
0x1800a7397  test    edx, edx
0x1800a7399  jz      short loc_1800A73E1
0x1800a739b  mov     eax, [r8+rsi+18h]
0x1800a73a0  mov     [rsp+2F0h+var_2B0], eax
0x1800a73a4  mov     rax, cs:PfSvcGlobals
0x1800a73ab  test    rax, rax
0x1800a73ae  jz      short loc_1800A73E1
0x1800a73b0  mov     rcx, [rax+1D8h]; RegHandle
0x1800a73b7  test    rcx, rcx
0x1800a73ba  jz      short loc_1800A73E1
0x1800a73bc  lea     rax, [rsp+2F0h+var_2B0]
0x1800a73c1  mov     qword ptr [rbp+1F0h+UserData.Size], 4
0x1800a73c9  lea     r9, [rbp+1F0h+UserData]; UserData
0x1800a73cd  mov     [rbp+1F0h+UserData.Ptr], rax
0x1800a73d1  mov     r8d, r10d; UserDataCount
0x1800a73d4  lea     rdx, HBDRV_EVENT_DISABLED_PERFORMANCE; EventDescriptor
0x1800a73db  call    cs:__imp_EventWrite
0x1800a73e1  mov     ebx, 4
0x1800a73e6  jmp     short loc_1800A73F2
0x1800a73e8  mov     ebx, 3
0x1800a73ed  jmp     short loc_1800A73F2
0x1800a73ef  mov     ebx, r10d
0x1800a73f2  mov     [rsp+2F0h+var_2B0], ebx
0x1800a73f6  cmp     [rbp+1F0h+arg_20], 0
0x1800a73fd  jnz     short loc_1800A745C
0x1800a73ff  mov     rcx, cs:PfSvcGlobals
0x1800a7406  lea     r8, [rbp+1F0h+var_250]
0x1800a740a  mov     r15, [rsp+2F0h+var_288]
0x1800a740f  add     rcx, 60h ; '`'
0x1800a7413  mov     r9d, 104h
0x1800a7419  mov     rdx, [r15]
0x1800a741c  mov     rdx, [rdx+r13*8+10h]
0x1800a7421  call    PfScStringCopy
0x1800a7426  xor     r13d, r13d
0x1800a7429  lea     r8, [rbp+1F0h+var_250]
0x1800a742d  mov     [rsp+2F0h+var_2B8], r13
0x1800a7432  lea     rcx, [rsp+2F0h+var_290]
0x1800a7437  mov     [rsp+2F0h+var_2C0], 1
0x1800a743f  mov     r9d, ebx
0x1800a7442  mov     [rsp+2F0h+var_2C8], r12d
0x1800a7447  mov     rdx, rdi
0x1800a744a  mov     dword ptr [rsp+2F0h+var_2D0], 1
0x1800a7452  call    PfsUpdateAttachState
0x1800a7457  jmp     loc_1800A72CE
0x1800a745c  xor     r13d, r13d
0x1800a745f  test    r14, r14
0x1800a7462  jz      short loc_1800A747A
0x1800a7464  mov     rcx, cs:PfSvcGlobals
0x1800a746b  mov     r8, r14; lpMem
0x1800a746e  xor     edx, edx; dwFlags
0x1800a7470  mov     rcx, [rcx+58h]; hHeap
0x1800a7474  call    cs:__imp_HeapFree
0x1800a747a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a747e  inc     rsi
0x1800a7481  cmp     [rdi+rsi*2], r13w
0x1800a7486  jnz     short loc_1800A747E
0x1800a7488  mov     rcx, cs:PfSvcGlobals
0x1800a748f  xor     edx, edx; dwFlags
0x1800a7491  movzx   r15d, si
0x1800a7495  mov     rcx, [rcx+58h]; hHeap
0x1800a7499  lea     eax, ds:28h[r15*2]
0x1800a74a1  lea     r8d, ds:28h[r15*2]; dwBytes
0x1800a74a9  mov     dword ptr [rsp+2F0h+Size], eax
0x1800a74ad  call    cs:__imp_HeapAlloc
0x1800a74b3  mov     r14, rax
0x1800a74b6  test    rax, rax
0x1800a74b9  jz      loc_1800A75B2
0x1800a74bf  mov     r8d, dword ptr [rsp+2F0h+Size]; Size
0x1800a74c4  xor     edx, edx; Val
0x1800a74c6  mov     rcx, rax; void *
0x1800a74c9  call    memset_0
0x1800a74ce  mov     [r14+0Ch], r13
0x1800a74d2  lea     edx, [r15+1]
0x1800a74d6  mov     [r14+14h], r13d
0x1800a74da  lea     rcx, [r14+22h]; pszDest
0x1800a74de  mov     dword ptr [r14+4], 8000h
0x1800a74e6  mov     eax, 1
0x1800a74eb  mov     [r14], eax
0x1800a74ee  add     rdx, rdx; cbDest
0x1800a74f1  mov     r8, rdi; pszSrc
0x1800a74f4  mov     dword ptr [r14+8], 6
0x1800a74fc  mov     [r14+18h], eax
0x1800a7500  mov     [r14+1Ch], ebx
0x1800a7504  mov     [r14+20h], si
0x1800a7509  call    StringCbCopyW
0x1800a750e  lea     rdx, [rsp+2F0h+Size]
0x1800a7513  mov     rcx, r14
0x1800a7516  call    cs:__imp_PfRpcSendCommand
0x1800a751c  mov     ebx, eax
0x1800a751e  test    eax, eax
0x1800a7520  jz      loc_1800A72C9
0x1800a7526  mov     rsi, qword ptr [rsp+2F0h+Size+4]
0x1800a752b  test    rdi, rdi
0x1800a752e  jz      short loc_1800A7546
0x1800a7530  mov     rcx, cs:PfSvcGlobals
0x1800a7537  mov     r8, rdi; lpMem
0x1800a753a  xor     edx, edx; dwFlags
0x1800a753c  mov     rcx, [rcx+58h]; hHeap
0x1800a7540  call    cs:__imp_HeapFree
0x1800a7546  lea     rcx, [rsp+2F0h+var_290]
0x1800a754b  call    PfsAttachStateCtxCleanup
0x1800a7550  test    rsi, rsi
0x1800a7553  jz      short loc_1800A755E
0x1800a7555  mov     rcx, rsi; Handle
0x1800a7558  call    cs:__imp_NtClose
0x1800a755e  test    r14, r14
0x1800a7561  jz      short loc_1800A7579
0x1800a7563  mov     rcx, cs:PfSvcGlobals
0x1800a756a  mov     r8, r14; lpMem
0x1800a756d  xor     edx, edx; dwFlags
0x1800a756f  mov     rcx, [rcx+58h]; hHeap
0x1800a7573  call    cs:__imp_HeapFree
0x1800a7579  mov     eax, ebx
0x1800a757b  mov     rcx, [rbp+1F0h+var_40]
0x1800a7582  xor     rcx, rsp; StackCookie
0x1800a7585  call    __security_check_cookie
0x1800a758a  mov     rbx, [rsp+2F0h+arg_10]
0x1800a7592  add     rsp, 2C0h
0x1800a7599  pop     r15
0x1800a759b  pop     r14
0x1800a759d  pop     r13
0x1800a759f  pop     r12
0x1800a75a1  pop     rdi
0x1800a75a2  pop     rsi
0x1800a75a3  pop     rbp
0x1800a75a4  retn
0x1800a75a5  mov     rsi, qword ptr [rsp+2F0h+Size+4]
0x1800a75aa  xor     r13d, r13d
0x1800a75ad  jmp     loc_1800A7310
0x1800a75b2  mov     ebx, 8
0x1800a75b7  jmp     loc_1800A7526
0x1800a75bc  mov     ebx, r13d
0x1800a75bf  jmp     loc_1800A752B
```
