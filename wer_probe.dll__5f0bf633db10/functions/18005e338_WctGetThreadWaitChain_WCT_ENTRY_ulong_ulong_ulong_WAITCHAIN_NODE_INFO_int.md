# WctGetThreadWaitChain(WCT_ENTRY *,ulong,ulong,ulong *,_WAITCHAIN_NODE_INFO *,int *)

- ea: `0x18005e338`
- end: `0x18005ea3c`
- name: `?WctGetThreadWaitChain@@YAKPEAUWCT_ENTRY@@KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z`
- size: `1796`
- prototype: `unsigned int(struct WCT_ENTRY *, unsigned int, unsigned int, unsigned int *, struct _WAITCHAIN_NODE_INFO *, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180036d60`
- `0x180036f30`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x18001c650`
- `0x18001fe24`
- `0x1800376a8`
- `0x18004c9d0`
- `0x1800517cc`
- `0x18005cb10`
- `0x18005cc68`
- `0x18005d450`
- `0x18005e1a4`
- `0x18005e338`
- `0x18005f4f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e954`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e954`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005e403`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005e403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e9b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e79d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e7c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e909`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e79d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e7c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e909`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WctGetThreadWaitChain(
        struct WCT_ENTRY *a1,
        char a2,
        DWORD a3,
        unsigned int *a4,
        struct _WAITCHAIN_NODE_INFO *a5,
        int *a6)
{
  __int64 v7; // rbx
  HANDLE v8; // rax
  DWORD v9; // eax
  DWORD LastError; // ebx
  unsigned int v11; // edx
  unsigned int v12; // r13d
  int v13; // r14d
  BOOL v14; // r15d
  unsigned int v15; // edi
  struct _SYSTEM_PROCESS_INFORMATION *v16; // r10
  struct _WAITCHAIN_NODE_INFO *v17; // rsi
  _OWORD *v18; // rcx
  _OWORD *v19; // rax
  __int64 v20; // rdx
  unsigned int ThreadInfo; // eax
  DWORD *p_ThreadId; // r8
  struct WCT_ENTRY *v23; // r15
  WCT_OBJECT_STATUS ObjectStatus; // ecx
  unsigned int i; // edx
  struct _WAITCHAIN_NODE_INFO *v26; // rcx
  struct _WAITCHAIN_NODE_INFO *v27; // rsi
  _OWORD *v28; // rcx
  _OWORD *v29; // rax
  __int64 v30; // rdx
  struct _SYSTEM_PROCESS_INFORMATION *v31; // r12
  unsigned int LockInfo; // eax
  unsigned int v33; // edx
  struct _WAITCHAIN_NODE_INFO *v34; // rsi
  int v35; // eax
  int v36; // r11d
  struct _WAITCHAIN_NODE_INFO *v37; // rcx
  struct _SYSTEM_PROCESS_INFORMATION *lpMem; // [rsp+58h] [rbp-B0h]
  unsigned int v40; // [rsp+60h] [rbp-A8h]
  unsigned int v41; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v42; // [rsp+68h] [rbp-A0h]
  struct _SYSTEM_PROCESS_INFORMATION *v43; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v44[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v45; // [rsp+80h] [rbp-88h] BYREF
  HANDLE hObject[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v47; // [rsp+98h] [rbp-70h]
  HWND (*v48)(unsigned int); // [rsp+A8h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-58h] BYREF
  int v50; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v51; // [rsp+BCh] [rbp-4Ch]
  _BYTE v52[288]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v53[336]; // [rsp+1F8h] [rbp+F0h] BYREF

  v7 = *a4;
  LODWORD(v42) = *a4;
  v45 = 0;
  v41 = 0;
  memset_0(v52, 0, 0x118u);
  *(_OWORD *)hObject = 0;
  v47 = 0;
  v43 = 0;
  v51 = 0;
  v49 = 0;
  v48 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  v50 = 10;
  *a6 = 0;
  memset_0(a5, 0, 280 * v7);
  v8 = OpenThread(0x48u, 0, a3);
  tlx::unique_any<tlx::file_handle_traits>::reset(&v45, v8);
  if ( v45 == -1 || v45 == 0 )
  {
    v15 = 0;
    LastError = GetLastError();
LABEL_89:
    if ( !LastError )
    {
LABEL_90:
      if ( !v15 )
        LastError = 1444;
    }
  }
  else
  {
    v9 = WctLoadUser32(&v49, &v48);
    LastError = v9;
    if ( !v9 || v9 == 50 )
    {
      LastError = WctCreateSystemSnapshot(&v43);
      if ( !LastError )
      {
        v11 = 0;
        v40 = 0;
        v12 = 0;
        v13 = 0;
        v14 = 0;
        v44[0] = a3;
        v15 = 0;
        v16 = v43;
        lpMem = v43;
        LastError = 1223;
        while ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 5, 0, 0) != 1 )
        {
          LastError = 1223;
          if ( v15 == 16 )
          {
            v23 = a1;
            v31 = lpMem;
            goto LABEL_64;
          }
          v44[1] = v15;
          if ( v13 || v15 >= (unsigned int)v42 )
          {
            v13 = 1;
            memset_0(v53, 0, 0x118u);
            v18 = v52;
            v19 = v53;
            v20 = 2;
            do
            {
              *v18 = *v19;
              v18[1] = v19[1];
              v18[2] = v19[2];
              v18[3] = v19[3];
              v18[4] = v19[4];
              v18[5] = v19[5];
              v18[6] = v19[6];
              v18[7] = v19[7];
              v18 += 8;
              v19 += 8;
              --v20;
            }
            while ( v20 );
            *v18 = *v19;
            *((_QWORD *)v18 + 2) = *((_QWORD *)v19 + 2);
            v17 = (struct _WAITCHAIN_NODE_INFO *)v52;
            v11 = v40;
            v16 = lpMem;
          }
          else
          {
            v17 = &a5[v15];
          }
          ++v15;
          if ( v14 )
          {
            v17->ObjectType = WctThreadType;
            v17->ObjectStatus = WctStatusPidOnlyRpcss;
            v17->ThreadObject.ProcessId = v41;
            p_ThreadId = &v17->ThreadObject.ThreadId;
            v17->ThreadObject.ThreadId = 0;
          }
          else
          {
            ThreadInfo = WctGetThreadInfo(a3, v16, v17, (struct _WCT_CLIENT_HANDLE *)hObject);
            v12 = ThreadInfo;
            if ( ThreadInfo )
            {
              if ( v15 <= 2 )
                goto LABEL_66;
              v23 = a1;
              if ( ThreadInfo == 5 )
              {
                v17->ObjectType = WctThreadType;
                v17->ObjectStatus = WctStatusNoAccess;
                v17->ThreadObject.ProcessId = v41;
                v17->ThreadObject.ThreadId = a3;
                v12 = 0;
                goto LABEL_67;
              }
              v34 = a5;
              a5[v15 - 2].ObjectStatus = WctStatusAbandoned;
LABEL_68:
              v31 = lpMem;
              goto LABEL_69;
            }
            v11 = v40;
            if ( !v40 )
              v11 = v47;
            v40 = v11;
            p_ThreadId = &v17->ThreadObject.ThreadId;
          }
          v23 = a1;
          if ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 5, 0, 0) == 1 )
            break;
          ObjectStatus = v17->ObjectStatus;
          if ( ((ObjectStatus - 3) & 0xFFFFFFFD) != 0
            || (a2 & 1) == 0 && (ObjectStatus == WctStatusPidOnlyRpcss || (_DWORD)v47 != v11) )
          {
            goto LABEL_67;
          }
          if ( !v13 )
          {
            for ( i = 0; i < v44[1]; ++i )
            {
              v26 = &a5[i];
              if ( v26->ObjectType == WctThreadType && v26->ThreadObject.ThreadId == *p_ThreadId )
              {
                v35 = WctCompareNode(v26, v17);
                v34 = a5;
                v31 = lpMem;
                if ( v35 )
                  *a6 = v36;
                goto LABEL_69;
              }
            }
          }
          if ( v15 == 16 )
            goto LABEL_67;
          if ( v13 || v15 >= (unsigned int)v42 )
          {
            v13 = 1;
            memset_0(v53, 0, 0x118u);
            v28 = v52;
            v29 = v53;
            v30 = 2;
            do
            {
              *v28 = *v29;
              v28[1] = v29[1];
              v28[2] = v29[2];
              v28[3] = v29[3];
              v28[4] = v29[4];
              v28[5] = v29[5];
              v28[6] = v29[6];
              v28[7] = v29[7];
              v28 += 8;
              v29 += 8;
              --v30;
            }
            while ( v30 );
            *v28 = *v29;
            *((_QWORD *)v28 + 2) = *((_QWORD *)v29 + 2);
            v27 = (struct _WAITCHAIN_NODE_INFO *)v52;
          }
          else
          {
            v27 = &a5[v15];
          }
          ++v15;
          v31 = lpMem;
          LockInfo = WctGetLockInfo(
                       a1,
                       v40,
                       (struct _WCT_CLIENT_HANDLE *)hObject,
                       (struct _WCT_LOCK_CONTEXT *)&v50,
                       a2,
                       lpMem,
                       v48,
                       v27,
                       v44,
                       &v41);
          v12 = LockInfo;
          if ( LockInfo )
          {
            if ( LockInfo == 1223 )
              break;
LABEL_64:
            v34 = a5;
LABEL_69:
            if ( hObject[0] )
            {
              CloseHandle(hObject[0]);
              hObject[0] = 0;
            }
            if ( hObject[1] )
            {
              CloseHandle(hObject[1]);
              hObject[1] = 0;
            }
            if ( _InterlockedCompareExchange((volatile signed __int32 *)v23 + 5, 0, 0) == 1 )
              break;
            if ( v12 && v15 )
              v13 = (unsigned int)v42 < --v15 ? v13 : 0;
            v43 = 0;
            if ( v31 )
              HeapFree(g_hWerheap, 0, v31);
            LastError = WctCreateSystemSnapshot(&v43);
            if ( LastError )
              break;
            if ( !v13 )
              *a4 = v15;
            if ( !(unsigned int)WctCheckChain(v43, a4, v34) )
            {
              *a6 = 0;
              goto LABEL_90;
            }
            if ( v13 )
            {
              *a4 = v15;
              LastError = 234;
            }
            if ( v15 == 16 )
            {
              LastError = 565;
              break;
            }
            goto LABEL_89;
          }
          if ( v27->ObjectStatus != WctStatusOwned )
            goto LABEL_64;
          v14 = v50 == 9;
          a3 = v44[0];
          if ( !v44[0] )
          {
            v33 = v41;
            if ( v41 )
            {
              if ( v50 != 9 )
              {
                if ( v15 != 16 )
                {
                  if ( v13 || v15 >= (unsigned int)v42 )
                  {
                    v13 = 1;
                    v37 = (struct _WAITCHAIN_NODE_INFO *)v52;
                    v34 = a5;
                  }
                  else
                  {
                    v34 = a5;
                    v37 = &a5[v15];
                  }
                  ++v15;
                  v37->ObjectType = WctThreadType;
                  v37->ThreadObject.ProcessId = v33;
                  v37->ThreadObject.ThreadId = 0;
                  v37->ObjectStatus = WctStatusPidOnly;
                  v23 = a1;
                  goto LABEL_68;
                }
LABEL_66:
                v23 = a1;
LABEL_67:
                v34 = a5;
                goto LABEL_68;
              }
            }
          }
          v11 = v40;
          v16 = lpMem;
          if ( v50 != 9 )
          {
            if ( hObject[0] )
            {
              CloseHandle(hObject[0]);
              hObject[0] = 0;
            }
            v11 = v40;
            v16 = lpMem;
            if ( hObject[1] )
            {
              CloseHandle(hObject[1]);
              hObject[1] = 0;
              v11 = v40;
              v16 = lpMem;
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_4c32fa7a72a13340317baef891270170_Traceguids, LastError);
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v49);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v43);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v45);
  return LastError;
}

```

## disassembly

```asm
0x18005e338  mov     rax, rsp
0x18005e33b  mov     [rax+18h], rbx
0x18005e33f  mov     [rax+20h], r9
0x18005e343  mov     [rax+10h], edx
0x18005e346  mov     [rax+8], rcx
0x18005e34a  push    rbp
0x18005e34b  push    rsi
0x18005e34c  push    rdi
0x18005e34d  push    r12
0x18005e34f  push    r13
0x18005e351  push    r14
0x18005e353  push    r15
0x18005e355  lea     rbp, [rax-248h]
0x18005e35c  sub     rsp, 310h
0x18005e363  mov     r12d, r8d
0x18005e366  mov     ebx, [r9]
0x18005e369  mov     dword ptr [rsp+340h+var_2E0], ebx
0x18005e36d  xor     r13d, r13d
0x18005e370  mov     [rsp+340h+var_2C8], r13
0x18005e375  mov     [rsp+340h+var_2E4], r13d
0x18005e37a  xor     edx, edx; Val
0x18005e37c  mov     r8d, 118h; Size
0x18005e382  lea     rcx, [rbp+240h+var_270]; void *
0x18005e386  call    memset_0
0x18005e38b  xorps   xmm0, xmm0
0x18005e38e  movups  xmmword ptr [rbp+240h+hObject], xmm0
0x18005e392  movups  [rbp+240h+var_2B0], xmm0
0x18005e396  mov     [rsp+340h+var_2D8], r13
0x18005e39b  movdqu  [rbp+240h+var_28C], xmm0
0x18005e3a0  mov     [rbp+240h+var_298], r13
0x18005e3a4  mov     [rbp+240h+var_2A0], r13
0x18005e3a8  lea     rax, WPP_GLOBAL_Control
0x18005e3af  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e3b6  cmp     rcx, rax
0x18005e3b9  jz      short loc_18005E3D5
0x18005e3bb  test    byte ptr [rcx+1Ch], 4
0x18005e3bf  jz      short loc_18005E3D5
0x18005e3c1  lea     edx, [r13+34h]
0x18005e3c5  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005e3cc  mov     rcx, [rcx+10h]
0x18005e3d0  call    WPP_SF_
0x18005e3d5  mov     [rbp+240h+var_290], 0Ah
0x18005e3dc  mov     rax, [rbp+240h+arg_28]
0x18005e3e3  mov     [rax], r13d
0x18005e3e6  imul    r8, rbx, 118h; Size
0x18005e3ed  xor     edx, edx; Val
0x18005e3ef  mov     rcx, [rbp+240h+arg_20]; void *
0x18005e3f6  call    memset_0
0x18005e3fb  mov     r8d, r12d; dwThreadId
0x18005e3fe  xor     edx, edx; bInheritHandle
0x18005e400  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18005e403  call    cs:__imp_OpenThread
0x18005e409  mov     rdx, rax
0x18005e40c  lea     rcx, [rsp+340h+var_2C8]
0x18005e411  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005e416  mov     rax, [rsp+340h+var_2C8]
0x18005e41b  inc     rax
0x18005e41e  cmp     rax, 1
0x18005e422  jbe     loc_18005E9B5
0x18005e428  lea     rdx, [rbp+240h+var_2A0]
0x18005e42c  lea     rcx, [rbp+240h+var_298]
0x18005e430  call    ?WctLoadUser32@@YAKPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6APEAUHWND__@@K@Z@Z; WctLoadUser32(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,HWND__ * (**)(ulong))
0x18005e435  mov     ebx, eax
0x18005e437  test    eax, eax
0x18005e439  jz      short loc_18005E444
0x18005e43b  cmp     eax, 32h ; '2'
0x18005e43e  jnz     loc_18005E9CE
0x18005e444  lea     rcx, [rsp+340h+var_2D8]
0x18005e449  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x18005e44e  mov     ebx, eax
0x18005e450  test    eax, eax
0x18005e452  jnz     loc_18005E9CE
0x18005e458  xor     edx, edx
0x18005e45a  mov     [rsp+340h+var_2E8], edx
0x18005e45e  xor     r13d, r13d
0x18005e461  xor     r14d, r14d
0x18005e464  xor     r15d, r15d
0x18005e467  mov     [rsp+340h+var_2D0], r12d
0x18005e46c  xor     edi, edi
0x18005e46e  mov     r10, [rsp+340h+var_2D8]
0x18005e473  mov     [rsp+340h+lpMem], r10
0x18005e478  mov     ebx, 4C7h
0x18005e47d  mov     r11d, 1
0x18005e483  xor     ecx, ecx
0x18005e485  xor     eax, eax
0x18005e487  mov     r8, [rbp+240h+arg_0]
0x18005e48e  lock cmpxchg [r8+14h], ecx
0x18005e494  cmp     eax, r11d
0x18005e497  jz      loc_18005E9CE
0x18005e49d  mov     ebx, 4C7h
0x18005e4a2  cmp     edi, 10h
0x18005e4a5  jz      loc_18005E8C8
0x18005e4ab  mov     [rsp+340h+var_2D0+4], edi
0x18005e4af  test    r14d, r14d
0x18005e4b2  jnz     short loc_18005E4CF
0x18005e4b4  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18005e4b8  jnb     short loc_18005E4CF
0x18005e4ba  mov     eax, edi
0x18005e4bc  imul    rsi, rax, 118h
0x18005e4c3  add     rsi, [rbp+240h+arg_20]
0x18005e4ca  jmp     loc_18005E569
0x18005e4cf  mov     r14d, r11d
0x18005e4d2  xor     edx, edx; Val
0x18005e4d4  mov     r8d, 118h; Size
0x18005e4da  lea     rcx, [rbp+240h+var_150]; void *
0x18005e4e1  call    memset_0
0x18005e4e6  lea     rcx, [rbp+240h+var_270]
0x18005e4ea  lea     rax, [rbp+240h+var_150]
0x18005e4f1  mov     edx, 2
0x18005e4f6  movups  xmm0, xmmword ptr [rax]
0x18005e4f9  movups  xmmword ptr [rcx], xmm0
0x18005e4fc  movups  xmm1, xmmword ptr [rax+10h]
0x18005e500  movups  xmmword ptr [rcx+10h], xmm1
0x18005e504  movups  xmm0, xmmword ptr [rax+20h]
0x18005e508  movups  xmmword ptr [rcx+20h], xmm0
0x18005e50c  movups  xmm1, xmmword ptr [rax+30h]
0x18005e510  movups  xmmword ptr [rcx+30h], xmm1
0x18005e514  movups  xmm0, xmmword ptr [rax+40h]
0x18005e518  movups  xmmword ptr [rcx+40h], xmm0
0x18005e51c  movups  xmm1, xmmword ptr [rax+50h]
0x18005e520  movups  xmmword ptr [rcx+50h], xmm1
0x18005e524  movups  xmm0, xmmword ptr [rax+60h]
0x18005e528  movups  xmmword ptr [rcx+60h], xmm0
0x18005e52c  movups  xmm1, xmmword ptr [rax+70h]
0x18005e530  movups  xmmword ptr [rcx+70h], xmm1
0x18005e534  lea     rcx, [rcx+80h]
0x18005e53b  lea     rax, [rax+80h]
0x18005e542  sub     rdx, 1
0x18005e546  jnz     short loc_18005E4F6
0x18005e548  movups  xmm0, xmmword ptr [rax]
0x18005e54b  movups  xmmword ptr [rcx], xmm0
0x18005e54e  mov     rax, [rax+10h]
0x18005e552  mov     [rcx+10h], rax
0x18005e556  lea     rsi, [rbp+240h+var_270]
0x18005e55a  mov     edx, [rsp+340h+var_2E8]
0x18005e55e  mov     r10, [rsp+340h+lpMem]
0x18005e563  mov     r11d, 1
0x18005e569  add     edi, r11d
0x18005e56c  test    r15d, r15d
0x18005e56f  jnz     short loc_18005E5A6
0x18005e571  lea     r9, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18005e575  mov     r8, rsi; struct _WAITCHAIN_NODE_INFO *
0x18005e578  mov     rdx, r10; struct _SYSTEM_PROCESS_INFORMATION *
0x18005e57b  mov     ecx, r12d; dwThreadId
0x18005e57e  call    ?WctGetThreadInfo@@YAKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_WAITCHAIN_NODE_INFO@@PEAU_WCT_CLIENT_HANDLE@@@Z; WctGetThreadInfo(ulong,_SYSTEM_PROCESS_INFORMATION *,_WAITCHAIN_NODE_INFO *,_WCT_CLIENT_HANDLE *)
0x18005e583  mov     r13d, eax
0x18005e586  test    eax, eax
0x18005e588  jnz     loc_18005E7E3
0x18005e58e  mov     edx, [rsp+340h+var_2E8]
0x18005e592  test    edx, edx
0x18005e594  cmovz   edx, dword ptr [rbp+240h+var_2B0]
0x18005e598  mov     [rsp+340h+var_2E8], edx
0x18005e59c  lea     r8, [rsi+0Ch]
0x18005e5a0  lea     r11d, [r15+1]
0x18005e5a4  jmp     short loc_18005E5C5
0x18005e5a6  mov     dword ptr [rsi], 8
0x18005e5ac  mov     dword ptr [rsi+4], 5
0x18005e5b3  mov     eax, [rsp+340h+var_2E4]
0x18005e5b7  mov     [rsi+8], eax
0x18005e5ba  lea     r8, [rsi+0Ch]
0x18005e5be  mov     dword ptr [r8], 0
0x18005e5c5  xor     ecx, ecx
0x18005e5c7  xor     eax, eax
0x18005e5c9  mov     r15, [rbp+240h+arg_0]
0x18005e5d0  lock cmpxchg [r15+14h], ecx
0x18005e5d6  cmp     eax, r11d
0x18005e5d9  jz      loc_18005E9CE
0x18005e5df  mov     ecx, [rsi+4]
0x18005e5e2  lea     eax, [rcx-3]
0x18005e5e5  test    eax, 0FFFFFFFDh
0x18005e5ea  jnz     loc_18005E8DD
0x18005e5f0  test    byte ptr [rbp+240h+arg_8], r11b
0x18005e5f7  jnz     short loc_18005E60B
0x18005e5f9  cmp     ecx, 5
0x18005e5fc  jz      loc_18005E8DD
0x18005e602  cmp     dword ptr [rbp+240h+var_2B0], edx
0x18005e605  jnz     loc_18005E8DD
0x18005e60b  test    r14d, r14d
0x18005e60e  jnz     short loc_18005E642
0x18005e610  xor     edx, edx
0x18005e612  mov     r9d, [rsp+340h+var_2D0+4]
0x18005e617  cmp     edx, r9d
0x18005e61a  jnb     short loc_18005E642
0x18005e61c  mov     eax, edx
0x18005e61e  imul    rcx, rax, 118h
0x18005e625  add     rcx, [rbp+240h+arg_20]; struct _WAITCHAIN_NODE_INFO *
0x18005e62c  cmp     dword ptr [rcx], 8
0x18005e62f  jnz     short loc_18005E63D
0x18005e631  mov     eax, [r8]
0x18005e634  cmp     [rcx+0Ch], eax
0x18005e637  jz      loc_18005E836
0x18005e63d  add     edx, r11d
0x18005e640  jmp     short loc_18005E617
0x18005e642  cmp     edi, 10h
0x18005e645  jz      loc_18005E8DD
0x18005e64b  test    r14d, r14d
0x18005e64e  jnz     short loc_18005E66B
0x18005e650  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18005e654  jnb     short loc_18005E66B
0x18005e656  mov     eax, edi
0x18005e658  imul    rsi, rax, 118h
0x18005e65f  add     rsi, [rbp+240h+arg_20]
0x18005e666  jmp     loc_18005E6F6
0x18005e66b  mov     r14d, r11d
0x18005e66e  xor     edx, edx; Val
0x18005e670  mov     r8d, 118h; Size
0x18005e676  lea     rcx, [rbp+240h+var_150]; void *
0x18005e67d  call    memset_0
0x18005e682  lea     rcx, [rbp+240h+var_270]
0x18005e686  lea     rax, [rbp+240h+var_150]
0x18005e68d  mov     edx, 2
0x18005e692  lea     r8d, [rdx+7Eh]
0x18005e696  movups  xmm0, xmmword ptr [rax]
0x18005e699  movups  xmmword ptr [rcx], xmm0
0x18005e69c  movups  xmm1, xmmword ptr [rax+10h]
0x18005e6a0  movups  xmmword ptr [rcx+10h], xmm1
0x18005e6a4  movups  xmm0, xmmword ptr [rax+20h]
0x18005e6a8  movups  xmmword ptr [rcx+20h], xmm0
0x18005e6ac  movups  xmm1, xmmword ptr [rax+30h]
0x18005e6b0  movups  xmmword ptr [rcx+30h], xmm1
0x18005e6b4  movups  xmm0, xmmword ptr [rax+40h]
0x18005e6b8  movups  xmmword ptr [rcx+40h], xmm0
0x18005e6bc  movups  xmm1, xmmword ptr [rax+50h]
0x18005e6c0  movups  xmmword ptr [rcx+50h], xmm1
0x18005e6c4  movups  xmm0, xmmword ptr [rax+60h]
0x18005e6c8  movups  xmmword ptr [rcx+60h], xmm0
0x18005e6cc  movups  xmm1, xmmword ptr [rax+70h]
0x18005e6d0  movups  xmmword ptr [rcx+70h], xmm1
0x18005e6d4  add     rcx, r8
0x18005e6d7  add     rax, r8
0x18005e6da  sub     rdx, 1
0x18005e6de  jnz     short loc_18005E696
0x18005e6e0  movups  xmm0, xmmword ptr [rax]
0x18005e6e3  movups  xmmword ptr [rcx], xmm0
0x18005e6e6  mov     rax, [rax+10h]
0x18005e6ea  mov     [rcx+10h], rax
0x18005e6ee  lea     rsi, [rbp+240h+var_270]
0x18005e6f2  lea     r11d, [rdx+1]
0x18005e6f6  add     edi, r11d
0x18005e6f9  lea     rax, [rsp+340h+var_2E4]
0x18005e6fe  mov     [rsp+340h+var_2F8], rax; unsigned int *
0x18005e703  lea     rax, [rsp+340h+var_2D0]
0x18005e708  mov     [rsp+340h+var_300], rax; unsigned int *
0x18005e70d  mov     [rsp+340h+var_308], rsi; struct _WAITCHAIN_NODE_INFO *
0x18005e712  mov     rax, [rbp+240h+var_2A0]
0x18005e716  mov     [rsp+340h+var_310], rax; HWND (*)(unsigned int)
0x18005e71b  mov     r12, [rsp+340h+lpMem]
0x18005e720  mov     [rsp+340h+var_318], r12; struct _SYSTEM_PROCESS_INFORMATION *
0x18005e725  mov     eax, [rbp+240h+arg_8]
0x18005e72b  mov     [rsp+340h+var_320], eax; unsigned int
0x18005e72f  lea     r9, [rbp+240h+var_290]; struct _WCT_LOCK_CONTEXT *
0x18005e733  lea     r8, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18005e737  mov     edx, [rsp+340h+var_2E8]; unsigned int
0x18005e73b  mov     rcx, r15; struct WCT_ENTRY *
0x18005e73e  call    ?WctGetLockInfo@@YAKPEAUWCT_ENTRY@@KPEAU_WCT_CLIENT_HANDLE@@PEAU_WCT_LOCK_CONTEXT@@KPEAU_SYSTEM_PROCESS_INFORMATION@@P6APEAUHWND__@@K@ZPEAU_WAITCHAIN_NODE_INFO@@PEAK6@Z; WctGetLockInfo(WCT_ENTRY *,ulong,_WCT_CLIENT_HANDLE *,_WCT_LOCK_CONTEXT *,ulong,_SYSTEM_PROCESS_INFORMATION *,HWND__ * (*)(ulong),_WAITCHAIN_NODE_INFO *,ulong *,ulong *)
0x18005e743  mov     r13d, eax
0x18005e746  test    eax, eax
0x18005e748  jnz     loc_18005E8B7
0x18005e74e  cmp     dword ptr [rsi+4], 6
0x18005e752  jnz     loc_18005E8BF
0x18005e758  xor     r15d, r15d
0x18005e75b  cmp     [rbp+240h+var_290], 9
0x18005e75f  lea     r11d, [rax+1]
0x18005e763  cmovz   r15d, r11d
0x18005e767  mov     r12d, [rsp+340h+var_2D0]
0x18005e76c  test    r12d, r12d
0x18005e76f  jnz     short loc_18005E782
0x18005e771  mov     edx, [rsp+340h+var_2E4]
0x18005e775  test    edx, edx
0x18005e777  jz      short loc_18005E782
0x18005e779  test    r15d, r15d
0x18005e77c  jz      loc_18005E861
0x18005e782  test    r15d, r15d
0x18005e785  mov     edx, [rsp+340h+var_2E8]
0x18005e789  mov     r10, [rsp+340h+lpMem]
0x18005e78e  jnz     loc_18005E483
0x18005e794  mov     rcx, [rbp+240h+hObject]; hObject
0x18005e798  test    rcx, rcx
0x18005e79b  jz      short loc_18005E7B1
0x18005e79d  call    cs:__imp_CloseHandle
0x18005e7a3  mov     [rbp+240h+hObject], 0
0x18005e7ab  mov     r11d, 1
0x18005e7b1  mov     rcx, [rbp+240h+hObject+8]; hObject
0x18005e7b5  test    rcx, rcx
0x18005e7b8  mov     edx, [rsp+340h+var_2E8]
0x18005e7bc  mov     r10, [rsp+340h+lpMem]
0x18005e7c1  jz      loc_18005E483
0x18005e7c7  call    cs:__imp_CloseHandle
0x18005e7cd  mov     [rbp+240h+hObject+8], 0
0x18005e7d5  mov     edx, [rsp+340h+var_2E8]
0x18005e7d9  mov     r10, [rsp+340h+lpMem]
0x18005e7de  jmp     loc_18005E47D
0x18005e7e3  cmp     edi, 2
0x18005e7e6  jbe     loc_18005E8D6
0x18005e7ec  mov     r15, [rbp+240h+arg_0]
0x18005e7f3  cmp     eax, 5
0x18005e7f6  jnz     short loc_18005E818
0x18005e7f8  mov     dword ptr [rsi], 8
0x18005e7fe  mov     dword ptr [rsi+4], 1
0x18005e805  mov     eax, [rsp+340h+var_2E4]
  ... truncated ...
```
