# WctGetThreadWaitChain(WCT_ENTRY *,ulong,ulong,ulong *,_WAITCHAIN_NODE_INFO *,int *)

- ea: `0x180060970`
- end: `0x18006109f`
- name: `?WctGetThreadWaitChain@@YAKPEAUWCT_ENTRY@@KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z`
- size: `1839`
- prototype: `unsigned int(struct WCT_ENTRY *, unsigned int, unsigned int, unsigned int *, struct _WAITCHAIN_NODE_INFO *, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180038d80`
- `0x180038f60`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x18001e0d0`
- `0x180020680`
- `0x180039760`
- `0x18004ed90`
- `0x180053d3c`
- `0x18005f04c`
- `0x18005f1a4`
- `0x18005fa0c`
- `0x1800607d0`
- `0x180060970`
- `0x180061c48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060faa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060faa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180060a3b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180060a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061014`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060ddb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060e0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060f3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060f59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060ddb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060e0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060f3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060f59`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, LastError);
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v49);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v43);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v45);
  return LastError;
}

```

## disassembly

```asm
0x180060970  mov     rax, rsp
0x180060973  mov     [rax+18h], rbx
0x180060977  mov     [rax+20h], r9
0x18006097b  mov     [rax+10h], edx
0x18006097e  mov     [rax+8], rcx
0x180060982  push    rbp
0x180060983  push    rsi
0x180060984  push    rdi
0x180060985  push    r12
0x180060987  push    r13
0x180060989  push    r14
0x18006098b  push    r15
0x18006098d  lea     rbp, [rax-248h]
0x180060994  sub     rsp, 310h
0x18006099b  mov     r12d, r8d
0x18006099e  mov     ebx, [r9]
0x1800609a1  mov     dword ptr [rsp+340h+var_2E0], ebx
0x1800609a5  xor     r13d, r13d
0x1800609a8  mov     [rsp+340h+var_2C8], r13
0x1800609ad  mov     [rsp+340h+var_2E4], r13d
0x1800609b2  xor     edx, edx; Val
0x1800609b4  mov     r8d, 118h; Size
0x1800609ba  lea     rcx, [rbp+240h+var_270]; void *
0x1800609be  call    memset_0
0x1800609c3  xorps   xmm0, xmm0
0x1800609c6  movups  xmmword ptr [rbp+240h+hObject], xmm0
0x1800609ca  movups  [rbp+240h+var_2B0], xmm0
0x1800609ce  mov     [rsp+340h+var_2D8], r13
0x1800609d3  movdqu  [rbp+240h+var_28C], xmm0
0x1800609d8  mov     [rbp+240h+var_298], r13
0x1800609dc  mov     [rbp+240h+var_2A0], r13
0x1800609e0  lea     rax, WPP_GLOBAL_Control
0x1800609e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800609ee  cmp     rcx, rax
0x1800609f1  jz      short loc_180060A0D
0x1800609f3  test    byte ptr [rcx+1Ch], 4
0x1800609f7  jz      short loc_180060A0D
0x1800609f9  lea     edx, [r13+34h]
0x1800609fd  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180060a04  mov     rcx, [rcx+10h]
0x180060a08  call    WPP_SF_
0x180060a0d  mov     [rbp+240h+var_290], 0Ah
0x180060a14  mov     rax, [rbp+240h+arg_28]
0x180060a1b  mov     [rax], r13d
0x180060a1e  imul    r8, rbx, 118h; Size
0x180060a25  xor     edx, edx; Val
0x180060a27  mov     rcx, [rbp+240h+arg_20]; void *
0x180060a2e  call    memset_0
0x180060a33  mov     r8d, r12d; dwThreadId
0x180060a36  xor     edx, edx; bInheritHandle
0x180060a38  lea     ecx, [rdx+48h]; dwDesiredAccess
0x180060a3b  call    cs:__imp_OpenThread
0x180060a42  nop     dword ptr [rax+rax+00h]
0x180060a47  mov     rdx, rax
0x180060a4a  lea     rcx, [rsp+340h+var_2C8]
0x180060a4f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180060a54  mov     rax, [rsp+340h+var_2C8]
0x180060a59  inc     rax
0x180060a5c  cmp     rax, 1
0x180060a60  jbe     loc_180061011
0x180060a66  lea     rdx, [rbp+240h+var_2A0]
0x180060a6a  lea     rcx, [rbp+240h+var_298]
0x180060a6e  call    ?WctLoadUser32@@YAKPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6APEAUHWND__@@K@Z@Z; WctLoadUser32(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,HWND__ * (**)(ulong))
0x180060a73  mov     ebx, eax
0x180060a75  test    eax, eax
0x180060a77  jz      short loc_180060A82
0x180060a79  cmp     eax, 32h ; '2'
0x180060a7c  jnz     loc_180061030
0x180060a82  lea     rcx, [rsp+340h+var_2D8]
0x180060a87  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x180060a8c  mov     ebx, eax
0x180060a8e  test    eax, eax
0x180060a90  jnz     loc_180061030
0x180060a96  xor     edx, edx
0x180060a98  mov     [rsp+340h+var_2E8], edx
0x180060a9c  xor     r13d, r13d
0x180060a9f  xor     r14d, r14d
0x180060aa2  xor     r15d, r15d
0x180060aa5  mov     [rsp+340h+var_2D0], r12d
0x180060aaa  xor     edi, edi
0x180060aac  mov     r10, [rsp+340h+var_2D8]
0x180060ab1  mov     [rsp+340h+lpMem], r10
0x180060ab6  mov     ebx, 4C7h
0x180060abb  mov     r11d, 1
0x180060ac1  xor     ecx, ecx
0x180060ac3  xor     eax, eax
0x180060ac5  mov     r8, [rbp+240h+arg_0]
0x180060acc  lock cmpxchg [r8+14h], ecx
0x180060ad2  cmp     eax, r11d
0x180060ad5  jz      loc_180061030
0x180060adb  mov     ebx, 4C7h
0x180060ae0  cmp     edi, 10h
0x180060ae3  jz      loc_180060F12
0x180060ae9  mov     [rsp+340h+var_2D0+4], edi
0x180060aed  test    r14d, r14d
0x180060af0  jnz     short loc_180060B0D
0x180060af2  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x180060af6  jnb     short loc_180060B0D
0x180060af8  mov     eax, edi
0x180060afa  imul    rsi, rax, 118h
0x180060b01  add     rsi, [rbp+240h+arg_20]
0x180060b08  jmp     loc_180060BA7
0x180060b0d  mov     r14d, r11d
0x180060b10  xor     edx, edx; Val
0x180060b12  mov     r8d, 118h; Size
0x180060b18  lea     rcx, [rbp+240h+var_150]; void *
0x180060b1f  call    memset_0
0x180060b24  lea     rcx, [rbp+240h+var_270]
0x180060b28  lea     rax, [rbp+240h+var_150]
0x180060b2f  mov     edx, 2
0x180060b34  movups  xmm0, xmmword ptr [rax]
0x180060b37  movups  xmmword ptr [rcx], xmm0
0x180060b3a  movups  xmm1, xmmword ptr [rax+10h]
0x180060b3e  movups  xmmword ptr [rcx+10h], xmm1
0x180060b42  movups  xmm0, xmmword ptr [rax+20h]
0x180060b46  movups  xmmword ptr [rcx+20h], xmm0
0x180060b4a  movups  xmm1, xmmword ptr [rax+30h]
0x180060b4e  movups  xmmword ptr [rcx+30h], xmm1
0x180060b52  movups  xmm0, xmmword ptr [rax+40h]
0x180060b56  movups  xmmword ptr [rcx+40h], xmm0
0x180060b5a  movups  xmm1, xmmword ptr [rax+50h]
0x180060b5e  movups  xmmword ptr [rcx+50h], xmm1
0x180060b62  movups  xmm0, xmmword ptr [rax+60h]
0x180060b66  movups  xmmword ptr [rcx+60h], xmm0
0x180060b6a  movups  xmm1, xmmword ptr [rax+70h]
0x180060b6e  movups  xmmword ptr [rcx+70h], xmm1
0x180060b72  lea     rcx, [rcx+80h]
0x180060b79  lea     rax, [rax+80h]
0x180060b80  sub     rdx, 1
0x180060b84  jnz     short loc_180060B34
0x180060b86  movups  xmm0, xmmword ptr [rax]
0x180060b89  movups  xmmword ptr [rcx], xmm0
0x180060b8c  mov     rax, [rax+10h]
0x180060b90  mov     [rcx+10h], rax
0x180060b94  lea     rsi, [rbp+240h+var_270]
0x180060b98  mov     edx, [rsp+340h+var_2E8]
0x180060b9c  mov     r10, [rsp+340h+lpMem]
0x180060ba1  mov     r11d, 1
0x180060ba7  add     edi, r11d
0x180060baa  test    r15d, r15d
0x180060bad  jnz     short loc_180060BE4
0x180060baf  lea     r9, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x180060bb3  mov     r8, rsi; struct _WAITCHAIN_NODE_INFO *
0x180060bb6  mov     rdx, r10; struct _SYSTEM_PROCESS_INFORMATION *
0x180060bb9  mov     ecx, r12d; dwThreadId
0x180060bbc  call    ?WctGetThreadInfo@@YAKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_WAITCHAIN_NODE_INFO@@PEAU_WCT_CLIENT_HANDLE@@@Z; WctGetThreadInfo(ulong,_SYSTEM_PROCESS_INFORMATION *,_WAITCHAIN_NODE_INFO *,_WCT_CLIENT_HANDLE *)
0x180060bc1  mov     r13d, eax
0x180060bc4  test    eax, eax
0x180060bc6  jnz     loc_180060E2D
0x180060bcc  mov     edx, [rsp+340h+var_2E8]
0x180060bd0  test    edx, edx
0x180060bd2  cmovz   edx, dword ptr [rbp+240h+var_2B0]
0x180060bd6  mov     [rsp+340h+var_2E8], edx
0x180060bda  lea     r8, [rsi+0Ch]
0x180060bde  lea     r11d, [r15+1]
0x180060be2  jmp     short loc_180060C03
0x180060be4  mov     dword ptr [rsi], 8
0x180060bea  mov     dword ptr [rsi+4], 5
0x180060bf1  mov     eax, [rsp+340h+var_2E4]
0x180060bf5  mov     [rsi+8], eax
0x180060bf8  lea     r8, [rsi+0Ch]
0x180060bfc  mov     dword ptr [r8], 0
0x180060c03  xor     ecx, ecx
0x180060c05  xor     eax, eax
0x180060c07  mov     r15, [rbp+240h+arg_0]
0x180060c0e  lock cmpxchg [r15+14h], ecx
0x180060c14  cmp     eax, r11d
0x180060c17  jz      loc_180061030
0x180060c1d  mov     ecx, [rsi+4]
0x180060c20  lea     eax, [rcx-3]
0x180060c23  test    eax, 0FFFFFFFDh
0x180060c28  jnz     loc_180060F27
0x180060c2e  test    byte ptr [rbp+240h+arg_8], r11b
0x180060c35  jnz     short loc_180060C49
0x180060c37  cmp     ecx, 5
0x180060c3a  jz      loc_180060F27
0x180060c40  cmp     dword ptr [rbp+240h+var_2B0], edx
0x180060c43  jnz     loc_180060F27
0x180060c49  test    r14d, r14d
0x180060c4c  jnz     short loc_180060C80
0x180060c4e  xor     edx, edx
0x180060c50  mov     r9d, [rsp+340h+var_2D0+4]
0x180060c55  cmp     edx, r9d
0x180060c58  jnb     short loc_180060C80
0x180060c5a  mov     eax, edx
0x180060c5c  imul    rcx, rax, 118h
0x180060c63  add     rcx, [rbp+240h+arg_20]; struct _WAITCHAIN_NODE_INFO *
0x180060c6a  cmp     dword ptr [rcx], 8
0x180060c6d  jnz     short loc_180060C7B
0x180060c6f  mov     eax, [r8]
0x180060c72  cmp     [rcx+0Ch], eax
0x180060c75  jz      loc_180060E80
0x180060c7b  add     edx, r11d
0x180060c7e  jmp     short loc_180060C55
0x180060c80  cmp     edi, 10h
0x180060c83  jz      loc_180060F27
0x180060c89  test    r14d, r14d
0x180060c8c  jnz     short loc_180060CA9
0x180060c8e  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x180060c92  jnb     short loc_180060CA9
0x180060c94  mov     eax, edi
0x180060c96  imul    rsi, rax, 118h
0x180060c9d  add     rsi, [rbp+240h+arg_20]
0x180060ca4  jmp     loc_180060D34
0x180060ca9  mov     r14d, r11d
0x180060cac  xor     edx, edx; Val
0x180060cae  mov     r8d, 118h; Size
0x180060cb4  lea     rcx, [rbp+240h+var_150]; void *
0x180060cbb  call    memset_0
0x180060cc0  lea     rcx, [rbp+240h+var_270]
0x180060cc4  lea     rax, [rbp+240h+var_150]
0x180060ccb  mov     edx, 2
0x180060cd0  lea     r8d, [rdx+7Eh]
0x180060cd4  movups  xmm0, xmmword ptr [rax]
0x180060cd7  movups  xmmword ptr [rcx], xmm0
0x180060cda  movups  xmm1, xmmword ptr [rax+10h]
0x180060cde  movups  xmmword ptr [rcx+10h], xmm1
0x180060ce2  movups  xmm0, xmmword ptr [rax+20h]
0x180060ce6  movups  xmmword ptr [rcx+20h], xmm0
0x180060cea  movups  xmm1, xmmword ptr [rax+30h]
0x180060cee  movups  xmmword ptr [rcx+30h], xmm1
0x180060cf2  movups  xmm0, xmmword ptr [rax+40h]
0x180060cf6  movups  xmmword ptr [rcx+40h], xmm0
0x180060cfa  movups  xmm1, xmmword ptr [rax+50h]
0x180060cfe  movups  xmmword ptr [rcx+50h], xmm1
0x180060d02  movups  xmm0, xmmword ptr [rax+60h]
0x180060d06  movups  xmmword ptr [rcx+60h], xmm0
0x180060d0a  movups  xmm1, xmmword ptr [rax+70h]
0x180060d0e  movups  xmmword ptr [rcx+70h], xmm1
0x180060d12  add     rcx, r8
0x180060d15  add     rax, r8
0x180060d18  sub     rdx, 1
0x180060d1c  jnz     short loc_180060CD4
0x180060d1e  movups  xmm0, xmmword ptr [rax]
0x180060d21  movups  xmmword ptr [rcx], xmm0
0x180060d24  mov     rax, [rax+10h]
0x180060d28  mov     [rcx+10h], rax
0x180060d2c  lea     rsi, [rbp+240h+var_270]
0x180060d30  lea     r11d, [rdx+1]
0x180060d34  add     edi, r11d
0x180060d37  lea     rax, [rsp+340h+var_2E4]
0x180060d3c  mov     [rsp+340h+var_2F8], rax; unsigned int *
0x180060d41  lea     rax, [rsp+340h+var_2D0]
0x180060d46  mov     [rsp+340h+var_300], rax; unsigned int *
0x180060d4b  mov     [rsp+340h+var_308], rsi; struct _WAITCHAIN_NODE_INFO *
0x180060d50  mov     rax, [rbp+240h+var_2A0]
0x180060d54  mov     [rsp+340h+var_310], rax; HWND (*)(unsigned int)
0x180060d59  mov     r12, [rsp+340h+lpMem]
0x180060d5e  mov     [rsp+340h+var_318], r12; struct _SYSTEM_PROCESS_INFORMATION *
0x180060d63  mov     eax, [rbp+240h+arg_8]
0x180060d69  mov     [rsp+340h+var_320], eax; unsigned int
0x180060d6d  lea     r9, [rbp+240h+var_290]; struct _WCT_LOCK_CONTEXT *
0x180060d71  lea     r8, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x180060d75  mov     edx, [rsp+340h+var_2E8]; unsigned int
0x180060d79  mov     rcx, r15; struct WCT_ENTRY *
0x180060d7c  call    ?WctGetLockInfo@@YAKPEAUWCT_ENTRY@@KPEAU_WCT_CLIENT_HANDLE@@PEAU_WCT_LOCK_CONTEXT@@KPEAU_SYSTEM_PROCESS_INFORMATION@@P6APEAUHWND__@@K@ZPEAU_WAITCHAIN_NODE_INFO@@PEAK6@Z; WctGetLockInfo(WCT_ENTRY *,ulong,_WCT_CLIENT_HANDLE *,_WCT_LOCK_CONTEXT *,ulong,_SYSTEM_PROCESS_INFORMATION *,HWND__ * (*)(ulong),_WAITCHAIN_NODE_INFO *,ulong *,ulong *)
0x180060d81  mov     r13d, eax
0x180060d84  test    eax, eax
0x180060d86  jnz     loc_180060F01
0x180060d8c  cmp     dword ptr [rsi+4], 6
0x180060d90  jnz     loc_180060F09
0x180060d96  xor     r15d, r15d
0x180060d99  cmp     [rbp+240h+var_290], 9
0x180060d9d  lea     r11d, [rax+1]
0x180060da1  cmovz   r15d, r11d
0x180060da5  mov     r12d, [rsp+340h+var_2D0]
0x180060daa  test    r12d, r12d
0x180060dad  jnz     short loc_180060DC0
0x180060daf  mov     edx, [rsp+340h+var_2E4]
0x180060db3  test    edx, edx
0x180060db5  jz      short loc_180060DC0
0x180060db7  test    r15d, r15d
0x180060dba  jz      loc_180060EAB
0x180060dc0  test    r15d, r15d
0x180060dc3  mov     edx, [rsp+340h+var_2E8]
0x180060dc7  mov     r10, [rsp+340h+lpMem]
0x180060dcc  jnz     loc_180060AC1
0x180060dd2  mov     rcx, [rbp+240h+hObject]; hObject
0x180060dd6  test    rcx, rcx
0x180060dd9  jz      short loc_180060DF5
0x180060ddb  call    cs:__imp_CloseHandle
0x180060de2  nop     dword ptr [rax+rax+00h]
0x180060de7  mov     [rbp+240h+hObject], 0
0x180060def  mov     r11d, 1
0x180060df5  mov     rcx, [rbp+240h+hObject+8]; hObject
0x180060df9  test    rcx, rcx
0x180060dfc  mov     edx, [rsp+340h+var_2E8]
0x180060e00  mov     r10, [rsp+340h+lpMem]
0x180060e05  jz      loc_180060AC1
0x180060e0b  call    cs:__imp_CloseHandle
0x180060e12  nop     dword ptr [rax+rax+00h]
0x180060e17  mov     [rbp+240h+hObject+8], 0
0x180060e1f  mov     edx, [rsp+340h+var_2E8]
0x180060e23  mov     r10, [rsp+340h+lpMem]
0x180060e28  jmp     loc_180060ABB
0x180060e2d  cmp     edi, 2
0x180060e30  jbe     loc_180060F20
0x180060e36  mov     r15, [rbp+240h+arg_0]
0x180060e3d  cmp     eax, 5
0x180060e40  jnz     short loc_180060E62
  ... truncated ...
```
