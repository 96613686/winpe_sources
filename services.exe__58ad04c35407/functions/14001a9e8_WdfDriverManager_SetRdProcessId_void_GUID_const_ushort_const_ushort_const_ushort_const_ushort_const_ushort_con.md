# WdfDriverManager::SetRdProcessId(void *,_GUID const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,DEBUG_MODE_FLAGS,_WUDF_SERVICE_TYPE)

- ea: `0x14001a9e8`
- end: `0x14001b09d`
- name: `?SetRdProcessId@WdfDriverManager@@QEAAEPEAXPEBU_GUID@@PEBG2222KUDEBUG_MODE_FLAGS@@W4_WUDF_SERVICE_TYPE@@@Z`
- size: `1717`
- prototype: `unsigned __int8 __high(void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct DEBUG_MODE_FLAGS, enum _WUDF_SERVICE_TYPE)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x14001a4ec`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14001a9e8`
- `0x14001b3d0`
- `0x14002db94`
- `0x140044300`
- `0x14008b290`
- `0x14008b2e4`
- `0x140091f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001af62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001afc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001af62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001afc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b01f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b01f`
- `RPCRT4!UuidToStringW` at `0x14001ac39`
- `RPCRT4!UuidToStringW` at `0x14001ac39`
- `RPCRT4!RpcStringFreeW` at `0x14001aba2`
- `RPCRT4!RpcStringFreeW` at `0x14001aba2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001af21`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001af21`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14001afb4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14001afb4`

## pseudocode

```c
bool __fastcall WdfDriverManager::SetRdProcessId(
        __int64 a1,
        __int64 a2,
        UUID *a3,
        const wchar_t *a4,
        STRSAFE_LPCWSTR a5,
        STRSAFE_LPCWSTR a6,
        STRSAFE_LPCWSTR a7,
        STRSAFE_PCNZWCH psz,
        int a9,
        char a10,
        int a11)
{
  char v11; // bl
  char v12; // al
  const wchar_t *v13; // r14
  bool v14; // r15
  unsigned __int128 v15; // rax
  __int64 v16; // r8
  PRPC_ASYNC_STATE v17; // r11
  signed int v18; // edi
  size_t v19; // r13
  unsigned __int64 v20; // r12
  __int64 v21; // rdx
  wchar_t *v23; // r14
  unsigned int v24; // eax
  HRESULT v25; // eax
  PRPC_ASYNC_STATE v26; // rcx
  int v27; // r9d
  int v28; // edx
  int v29; // r10d
  size_t v30; // r11
  size_t v31; // r11
  int v32; // r10d
  unsigned int v33; // r11d
  int v34; // eax
  WdfDriverManager *v35; // rbx
  __int64 v36; // rax
  const WCHAR *v37; // rbx
  HANDLE FileW; // rax
  char LastError; // al
  DWORD v40; // eax
  __int64 v41; // rdx
  RPC_WSTR String; // [rsp+60h] [rbp-20h] BYREF
  size_t pcchLength; // [rsp+68h] [rbp-18h] BYREF
  WdfDriverManager *v44; // [rsp+70h] [rbp-10h]
  DWORD BytesReturned; // [rsp+C0h] [rbp+40h] BYREF
  int v46; // [rsp+C4h] [rbp+44h]
  __int64 v47; // [rsp+C8h] [rbp+48h]
  UUID *Uuid; // [rsp+D0h] [rbp+50h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+D8h] [rbp+58h]

  pszSrc = a4;
  Uuid = a3;
  v47 = a2;
  v46 = HIDWORD(a1);
  v44 = DrvMgrExt;
  String = 0;
  pcchLength = 0;
  BytesReturned = 0;
  v11 = a10;
  if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
    || *((int *)&WPP_GLOBAL_Control->u.NotificationRoutine + 5) >= 0 )
  {
    v13 = psz;
  }
  else
  {
    if ( (a10 & 1) != 0 )
      v12 = a10 & 6 | 1;
    else
      v12 = 0;
    v13 = psz;
    WPP_SF_q_guid_SSSSSdD(
      (TRACEHANDLE)WPP_GLOBAL_Control->u.APC.hThread,
      (__int64)a3,
      (__int64)a4,
      (__int64)a5,
      (__int64)a6,
      (__int64)a7,
      (__int64)psz,
      a9,
      v12);
  }
  v14 = 0;
  LODWORD(v15) = StringCchLengthW(v13, 0xFFFFu, &pcchLength);
  v18 = v15;
  if ( (v15 & 0x80000000) == 0LL )
  {
    v19 = pcchLength + 1;
    pcchLength = 0;
    v15 = v19 * (unsigned __int128)2uLL;
    if ( is_mul_ok(v19, 2u) )
    {
      v20 = 2 * v19 + 1132;
      if ( 2 * v19 < 0xFFFFFFFFFFFFFB94uLL )
      {
        v18 = 0;
        if ( v20 > 0xFFFF )
        {
          if ( v17 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (*((_BYTE *)&v17->u.NotificationRoutine + 20) & 1) == 0
            || *((_BYTE *)&v17->u.NotificationRoutine + 17) < 2u )
          {
            goto LABEL_23;
          }
          v21 = 62;
          goto LABEL_22;
        }
        v23 = (wchar_t *)operator new(
                           2 * v19 + 1132,
                           (const struct std::nothrow_t *)((v19 * (unsigned __int128)2uLL) >> 64));
        if ( !v23 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
            || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
          {
            goto LABEL_23;
          }
          v21 = 63;
LABEL_22:
          WPP_SF_d(v17->u.APC.hThread, v21, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, (unsigned int)v20);
          v17 = WPP_GLOBAL_Control;
          goto LABEL_23;
        }
        pcchLength = 0;
        v24 = UuidToStringW(Uuid, &String);
        v18 = v24;
        if ( v24 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
            && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 64, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, v24);
          }
          if ( v18 > 0 )
            v18 = (unsigned __int16)v18 | 0x80070000;
          goto LABEL_91;
        }
        v25 = StringCchCopyW(v23 + 524, 0x27u, String);
        v18 = v25;
        if ( v25 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
            && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
          {
            v27 = (int)String;
            v28 = 65;
LABEL_47:
            WPP_SF_Sd(v26->u.APC.hThread, v28, (unsigned int)&WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, v27, v25);
            goto LABEL_91;
          }
          goto LABEL_91;
        }
        v25 = StringCchCopyW(v23 + 12, 0x80u, pszSrc);
        v18 = v25;
        if ( v25 >= 0 )
        {
          v25 = StringCchCopyW(v23 + 140, v30, a5);
          v18 = v25;
          if ( v25 >= 0 )
          {
            v25 = StringCchCopyW(v23 + 268, v31, a6);
            v18 = v25;
            if ( v25 >= 0 )
            {
              if ( (unsigned int)(a11 - 1) > 2 )
              {
                v25 = StringCchCopyW(v23 + 396, 0x80u, a7);
                v18 = v25;
                if ( v25 < 0 )
                {
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
                    && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                  {
                    v27 = (int)a7;
                    v28 = 69;
                    goto LABEL_47;
                  }
                  goto LABEL_91;
                }
              }
              else
              {
                v23[396] = 0;
              }
              v25 = StringCchCopyW(v23 + 566, v19, psz);
              v18 = v25;
              if ( v25 >= 0 )
              {
                *((_QWORD *)v23 + 1) = v47;
                *((_DWORD *)v23 + 4) = a9;
                *(_BYTE *)v23 = 28;
                if ( (v11 & 1) != 0 )
                  v34 = v11 & 6 | 1;
                else
                  v34 = 0;
                v35 = v44;
                *((_DWORD *)v23 + 5) = v34;
                v36 = 152;
                *((_DWORD *)v23 + 282) = v32;
                if ( v33 <= 2 )
                  v36 = 160;
                v37 = *(const WCHAR **)((char *)v35 + v36);
                FileW = CreateFileW(v37, 0xC0000000, 0, 0, 3u, 0x80u, 0);
                pcchLength = (size_t)FileW;
                if ( FileW == (HANDLE)-1LL )
                {
                  pcchLength = 0;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
                    && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                  {
                    LastError = GetLastError();
                    WPP_SF_Sd(
                      WPP_GLOBAL_Control->u.APC.hThread,
                      71,
                      (unsigned int)&WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids,
                      (_DWORD)v37,
                      LastError);
                  }
                }
                else
                {
                  v14 = DeviceIoControl(FileW, 0x80018400, v23, v20, 0, 0, &BytesReturned, 0);
                  if ( !v14 )
                  {
                    v40 = GetLastError();
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->u.APC.hThread,
                        72,
                        &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids,
                        v40);
                    }
                  }
                }
                goto LABEL_91;
              }
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
                && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
              {
                v27 = (int)psz;
                v28 = 70;
                goto LABEL_47;
              }
LABEL_91:
              operator delete(v23);
              if ( pcchLength )
                CloseHandle((HANDLE)pcchLength);
              goto LABEL_14;
            }
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
              || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
            {
              goto LABEL_91;
            }
            v28 = 68;
          }
          else
          {
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
              || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
            {
              goto LABEL_91;
            }
            v28 = 67;
          }
        }
        else
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
            || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
          {
            goto LABEL_91;
          }
          v28 = v30 - 62;
        }
        v27 = v29;
        goto LABEL_47;
      }
      v18 = -2147024362;
      if ( v17 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&v17->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&v17->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_23;
      }
      v41 = 61;
    }
    else
    {
      v18 = -2147024362;
      if ( v17 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&v17->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&v17->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_23;
      }
      v41 = 60;
    }
    WPP_SF_d(v17->u.APC.hThread, v41, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, (unsigned int)v19);
    goto LABEL_14;
  }
  if ( v17 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&v17->u.NotificationRoutine + 20) & 1) != 0
    && *((_BYTE *)&v17->u.NotificationRoutine + 17) >= 2u )
  {
    WPP_SF_Sd(v17->u.APC.hThread, 59, (unsigned int)&WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, (_DWORD)v13, v15);
LABEL_14:
    v17 = WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( String )
  {
    RpcStringFreeW(&String);
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&v17->u.NotificationRoutine + 20) & 1) != 0
    && *((int *)&v17->u.NotificationRoutine + 5) < 0 )
  {
    WPP_SF_ld(v17->u.APC.hThread, *((_QWORD *)&v15 + 1), v16, v14, v18);
  }
  return v14;
}

```

## disassembly

```asm
0x14001a9e8  mov     rax, rsp
0x14001a9eb  mov     [rax+20h], r9
0x14001a9ef  mov     [rax+18h], r8
0x14001a9f3  mov     [rax+10h], rdx
0x14001a9f7  mov     [rax+8], rcx
0x14001a9fb  push    rbp
0x14001a9fc  push    rbx
0x14001a9fd  push    rdi
0x14001a9fe  push    r12
0x14001aa00  push    r13
0x14001aa02  push    r14
0x14001aa04  push    r15
0x14001aa06  mov     rbp, rsp
0x14001aa09  sub     rsp, 80h
0x14001aa10  mov     rax, cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA; WdfDriverManager * DrvMgrExt
0x14001aa17  xor     edi, edi
0x14001aa19  mov     [rbp+var_10], rax
0x14001aa1d  mov     [rbp+String], rdi
0x14001aa21  mov     [rbp+pcchLength], rdi
0x14001aa25  mov     [rbp+BytesReturned], edi
0x14001aa28  mov     r11, cs:WPP_GLOBAL_Control
0x14001aa2f  lea     r12, WPP_GLOBAL_Control
0x14001aa36  movzx   ebx, [rbp+arg_48]
0x14001aa3d  cmp     r11, r12
0x14001aa40  jz      short loc_14001AAB1
0x14001aa42  test    byte ptr [r11+44h], 1
0x14001aa47  jz      short loc_14001AAB1
0x14001aa49  cmp     [r11+44h], edi
0x14001aa4d  jge     short loc_14001AAB1
0x14001aa4f  test    bl, 1
0x14001aa52  jnz     short loc_14001AA58
0x14001aa54  mov     eax, edi
0x14001aa56  jmp     short loc_14001AA60
0x14001aa58  mov     eax, ebx
0x14001aa5a  and     eax, 6
0x14001aa5d  or      eax, 1
0x14001aa60  mov     r14, [rbp+psz]
0x14001aa64  mov     rcx, [r11+38h]; LoggerHandle
0x14001aa68  mov     dword ptr [rsp+80h+var_28], eax; char
0x14001aa6c  mov     eax, [rbp+arg_40]
0x14001aa72  mov     dword ptr [rsp+80h+var_30], eax; char
0x14001aa76  mov     rax, [rbp+arg_30]
0x14001aa7a  mov     [rsp+80h+var_38], r14; __int64
0x14001aa7f  mov     [rsp+80h+var_40], rax; __int64
0x14001aa84  mov     rax, [rbp+arg_28]
0x14001aa88  mov     [rsp+80h+lpOverlapped], rax; __int64
0x14001aa8d  mov     rax, [rbp+arg_20]
0x14001aa91  mov     [rsp+80h+hTemplateFile], rax; __int64
0x14001aa96  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r9; __int64
0x14001aa9b  mov     r9, rdx
0x14001aa9e  mov     qword ptr [rsp+80h+dwCreationDisposition], r8; __int64
0x14001aaa3  call    WPP_SF_q_guid_SSSSSdD
0x14001aaa8  mov     r11, cs:WPP_GLOBAL_Control
0x14001aaaf  jmp     short loc_14001AAB5
0x14001aab1  mov     r14, [rbp+psz]
0x14001aab5  lea     r8, [rbp+pcchLength]; pcchLength
0x14001aab9  mov     edx, 0FFFFh; cchMax
0x14001aabe  mov     rcx, r14; psz
0x14001aac1  mov     r15b, dil
0x14001aac4  call    StringCchLengthW
0x14001aac9  mov     edi, eax
0x14001aacb  test    eax, eax
0x14001aacd  jns     short loc_14001AB16
0x14001aacf  cmp     r11, r12; __annotation("TMF:",
0x14001aad2  jz      loc_14001AB97
0x14001aad8  test    byte ptr [r11+44h], 1
0x14001aadd  jz      loc_14001AB97
0x14001aae3  cmp     byte ptr [r11+41h], 2
0x14001aae8  jb      loc_14001AB97
0x14001aaee  mov     rcx, [r11+38h]
0x14001aaf2  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14001aaf9  mov     edx, 3Bh ; ';'
0x14001aafe  mov     [rsp+80h+dwCreationDisposition], eax
0x14001ab02  mov     r9, r14
0x14001ab05  call    WPP_SF_Sd
0x14001ab0a  mov     r11, cs:WPP_GLOBAL_Control
0x14001ab11  jmp     loc_14001AB97
0x14001ab16  mov     r13, [rbp+pcchLength]
0x14001ab1a  mov     eax, 2
0x14001ab1f  inc     r13
0x14001ab22  mov     [rbp+pcchLength], 0
0x14001ab2a  mul     r13
0x14001ab2d  test    rdx, rdx
0x14001ab30  jnz     loc_14001B072
0x14001ab36  lea     r12, [rax+46Ch]
0x14001ab3d  cmp     r12, 46Ch
0x14001ab44  jb      loc_14001B02A
0x14001ab4a  xor     edi, edi
0x14001ab4c  cmp     r12, 0FFFFh
0x14001ab53  jbe     loc_14001ABE9
0x14001ab59  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ab60  cmp     r11, rax
0x14001ab63  jz      short loc_14001AB90
0x14001ab65  test    byte ptr [r11+44h], 1
0x14001ab6a  jz      short loc_14001AB90
0x14001ab6c  cmp     byte ptr [r11+41h], 2
0x14001ab71  jb      short loc_14001AB90
0x14001ab73  lea     edx, [rdi+3Eh]
0x14001ab76  mov     rcx, [r11+38h]
0x14001ab7a  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14001ab81  mov     r9d, r12d
0x14001ab84  call    WPP_SF_d
0x14001ab89  mov     r11, cs:WPP_GLOBAL_Control
0x14001ab90  lea     r12, WPP_GLOBAL_Control
0x14001ab97  cmp     [rbp+String], 0
0x14001ab9c  jz      short loc_14001ABAF
0x14001ab9e  lea     rcx, [rbp+String]; String
0x14001aba2  call    cs:__imp_RpcStringFreeW
0x14001aba8  mov     r11, cs:WPP_GLOBAL_Control
0x14001abaf  cmp     r11, r12
0x14001abb2  jz      short loc_14001ABD3
0x14001abb4  test    byte ptr [r11+44h], 1
0x14001abb9  jz      short loc_14001ABD3
0x14001abbb  cmp     dword ptr [r11+44h], 0
0x14001abc0  jge     short loc_14001ABD3
0x14001abc2  mov     rcx, [r11+38h]
0x14001abc6  movzx   r9d, r15b
0x14001abca  mov     [rsp+80h+dwCreationDisposition], edi
0x14001abce  call    WPP_SF_ld
0x14001abd3  mov     al, r15b
0x14001abd6  add     rsp, 80h
0x14001abdd  pop     r15
0x14001abdf  pop     r14
0x14001abe1  pop     r13
0x14001abe3  pop     r12
0x14001abe5  pop     rdi
0x14001abe6  pop     rbx
0x14001abe7  pop     rbp
0x14001abe8  retn
0x14001abe9  mov     rcx, r12; Size
0x14001abec  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14001abf1  mov     r14, rax
0x14001abf4  test    rax, rax
0x14001abf7  jnz     short loc_14001AC2B
0x14001abf9  mov     r11, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ac00  lea     rax, WPP_GLOBAL_Control
0x14001ac07  cmp     r11, rax
0x14001ac0a  jz      short loc_14001AB90
0x14001ac0c  test    byte ptr [r11+44h], 1
0x14001ac11  jz      loc_14001AB90
0x14001ac17  cmp     byte ptr [r11+41h], 2
0x14001ac1c  jb      loc_14001AB90
0x14001ac22  lea     edx, [r14+3Fh]
0x14001ac26  jmp     loc_14001AB76
0x14001ac2b  mov     rcx, [rbp+Uuid]; Uuid
0x14001ac2f  lea     rdx, [rbp+String]; StringUuid
0x14001ac33  xor     eax, eax
0x14001ac35  mov     [rbp+pcchLength], rax
0x14001ac39  call    cs:__imp_UuidToStringW
0x14001ac3f  mov     edi, eax
0x14001ac41  test    eax, eax
0x14001ac43  jz      short loc_14001AC92
0x14001ac45  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ac4c  lea     r12, WPP_GLOBAL_Control
0x14001ac53  cmp     rcx, r12
0x14001ac56  jz      short loc_14001AC7C
0x14001ac58  test    byte ptr [rcx+44h], 8
0x14001ac5c  jz      short loc_14001AC7C
0x14001ac5e  cmp     byte ptr [rcx+41h], 2
0x14001ac62  jb      short loc_14001AC7C
0x14001ac64  mov     rcx, [rcx+38h]
0x14001ac68  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14001ac6f  mov     edx, 40h ; '@'
0x14001ac74  mov     r9d, eax
0x14001ac77  call    WPP_SF_d
0x14001ac7c  test    edi, edi
0x14001ac7e  jle     loc_14001B007
0x14001ac84  movzx   edi, di
0x14001ac87  or      edi, 80070000h
0x14001ac8d  jmp     loc_14001B007
0x14001ac92  mov     r8, [rbp+String]; pszSrc
0x14001ac96  lea     rcx, [r14+418h]; pszDest
0x14001ac9d  mov     edx, 27h ; '''; cchDest
0x14001aca2  call    StringCchCopyW
0x14001aca7  mov     edi, eax
0x14001aca9  test    eax, eax
0x14001acab  jns     short loc_14001ACFA
0x14001acad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001acb4  lea     r12, WPP_GLOBAL_Control
0x14001acbb  cmp     rcx, r12
0x14001acbe  jz      loc_14001B007
0x14001acc4  test    byte ptr [rcx+44h], 1
0x14001acc8  jz      loc_14001B007
0x14001acce  cmp     byte ptr [rcx+41h], 2
0x14001acd2  jb      loc_14001B007
0x14001acd8  mov     r9, [rbp+String]
0x14001acdc  mov     edx, 41h ; 'A'
0x14001ace1  mov     rcx, [rcx+38h]
0x14001ace5  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14001acec  mov     [rsp+80h+dwCreationDisposition], eax
0x14001acf0  call    WPP_SF_Sd
0x14001acf5  jmp     loc_14001B007
0x14001acfa  mov     r10, [rbp+pszSrc]
0x14001acfe  lea     rcx, [r14+18h]; pszDest
0x14001ad02  mov     r11d, 80h
0x14001ad08  mov     r8, r10; pszSrc
0x14001ad0b  mov     edx, r11d; cchDest
0x14001ad0e  call    StringCchCopyW
0x14001ad13  mov     edi, eax
0x14001ad15  test    eax, eax
0x14001ad17  jns     short loc_14001AD4D
0x14001ad19  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ad20  lea     r12, WPP_GLOBAL_Control
0x14001ad27  cmp     rcx, r12
0x14001ad2a  jz      loc_14001B007
0x14001ad30  test    byte ptr [rcx+44h], 1
0x14001ad34  jz      loc_14001B007
0x14001ad3a  cmp     byte ptr [rcx+41h], 2
0x14001ad3e  jb      loc_14001B007
0x14001ad44  lea     edx, [r11-3Eh]
0x14001ad48  mov     r9, r10
0x14001ad4b  jmp     short loc_14001ACE1
0x14001ad4d  mov     r10, [rbp+arg_20]
0x14001ad51  lea     rcx, [r14+118h]; pszDest
0x14001ad58  mov     r8, r10; pszSrc
0x14001ad5b  mov     rdx, r11; cchDest
0x14001ad5e  call    StringCchCopyW
0x14001ad63  mov     edi, eax
0x14001ad65  test    eax, eax
0x14001ad67  jns     short loc_14001AD9B
0x14001ad69  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ad70  lea     r12, WPP_GLOBAL_Control
0x14001ad77  cmp     rcx, r12
0x14001ad7a  jz      loc_14001B007
0x14001ad80  test    byte ptr [rcx+44h], 1
0x14001ad84  jz      loc_14001B007
0x14001ad8a  cmp     byte ptr [rcx+41h], 2
0x14001ad8e  jb      loc_14001B007
0x14001ad94  mov     edx, 43h ; 'C'
0x14001ad99  jmp     short loc_14001AD48
0x14001ad9b  mov     r10, [rbp+arg_28]
0x14001ad9f  lea     rcx, [r14+218h]; pszDest
0x14001ada6  mov     r8, r10; pszSrc
0x14001ada9  mov     rdx, r11; cchDest
0x14001adac  call    StringCchCopyW
0x14001adb1  mov     edi, eax
0x14001adb3  test    eax, eax
0x14001adb5  jns     short loc_14001ADEC
0x14001adb7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001adbe  lea     r12, WPP_GLOBAL_Control
0x14001adc5  cmp     rcx, r12
0x14001adc8  jz      loc_14001B007
0x14001adce  test    byte ptr [rcx+44h], 1
0x14001add2  jz      loc_14001B007
0x14001add8  cmp     byte ptr [rcx+41h], 2
0x14001addc  jb      loc_14001B007
0x14001ade2  mov     edx, 44h ; 'D'
0x14001ade7  jmp     loc_14001AD48
0x14001adec  mov     r10d, [rbp+arg_50]
0x14001adf3  lea     r11d, [r10-1]
0x14001adf7  cmp     r11d, 2
0x14001adfb  ja      short loc_14001AE5D
0x14001adfd  xor     eax, eax
0x14001adff  mov     [r14+318h], ax
0x14001ae07  mov     r8, [rbp+psz]; pszSrc
0x14001ae0b  lea     rcx, [r14+46Ch]; pszDest
0x14001ae12  mov     rdx, r13; cchDest
0x14001ae15  call    StringCchCopyW
0x14001ae1a  mov     edi, eax
0x14001ae1c  test    eax, eax
0x14001ae1e  jns     loc_14001AEB1
0x14001ae24  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ae2b  lea     r12, WPP_GLOBAL_Control
0x14001ae32  cmp     rcx, r12
0x14001ae35  jz      loc_14001B007
0x14001ae3b  test    byte ptr [rcx+44h], 1
0x14001ae3f  jz      loc_14001B007
0x14001ae45  cmp     byte ptr [rcx+41h], 2
0x14001ae49  jb      loc_14001B007
0x14001ae4f  mov     r9, [rbp+psz]
0x14001ae53  mov     edx, 46h ; 'F'
0x14001ae58  jmp     loc_14001ACE1
0x14001ae5d  mov     r8, [rbp+arg_30]; pszSrc
0x14001ae61  lea     rcx, [r14+318h]; pszDest
0x14001ae68  mov     edx, 80h; cchDest
0x14001ae6d  call    StringCchCopyW
0x14001ae72  mov     edi, eax
0x14001ae74  test    eax, eax
0x14001ae76  jns     short loc_14001AE07
0x14001ae78  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ae7f  lea     r12, WPP_GLOBAL_Control
0x14001ae86  cmp     rcx, r12
0x14001ae89  jz      loc_14001B007
0x14001ae8f  test    byte ptr [rcx+44h], 1
0x14001ae93  jz      loc_14001B007
0x14001ae99  cmp     byte ptr [rcx+41h], 2
0x14001ae9d  jb      loc_14001B007
0x14001aea3  mov     r9, [rbp+arg_30]
0x14001aea7  mov     edx, 45h ; 'E'
0x14001aeac  jmp     loc_14001ACE1
0x14001aeb1  mov     rax, [rbp+arg_8]
0x14001aeb5  mov     [r14+8], rax
0x14001aeb9  mov     eax, [rbp+arg_40]
0x14001aebf  mov     [r14+10h], eax
0x14001aec3  mov     byte ptr [r14], 1Ch
0x14001aec7  test    bl, 1
0x14001aeca  jnz     short loc_14001AED0
0x14001aecc  xor     eax, eax
0x14001aece  jmp     short loc_14001AED8
0x14001aed0  mov     eax, ebx
  ... truncated ...
```
