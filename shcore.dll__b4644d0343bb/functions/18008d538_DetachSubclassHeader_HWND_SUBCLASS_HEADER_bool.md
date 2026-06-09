# DetachSubclassHeader(HWND__ *,SUBCLASS_HEADER *,bool)

- ea: `0x18008d538`
- end: `0x18008d821`
- name: `?DetachSubclassHeader@@YAXPEAUHWND__@@PEAUSUBCLASS_HEADER@@_N@Z`
- size: `745`
- prototype: `void __fastcall(HWND, struct SUBCLASS_HEADER *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180039b70`
- `0x18008d458`

## callees

- `0x180039640`
- `0x180039de4`
- `0x18004b4d8`
- `0x18008c6a0`
- `0x18008cd60`
- `0x18008ce84`
- `0x18008d538`
- `0x18008d95c`
- `0x180093204`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d7c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008d73c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008d73c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d5fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d5fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18008d754`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18008d754`

## pseudocode

```c
void __fastcall DetachSubclassHeader(HWND a1, struct SUBCLASS_HEADER *a2, char a3)
{
  struct SUBCLASS_HEADER *SubclassHeader; // rax
  bool v4; // [rsp+30h] [rbp-48h] BYREF
  bool v5; // [rsp+31h] [rbp-47h] BYREF
  bool v6; // [rsp+32h] [rbp-46h] BYREF
  bool v7; // [rsp+33h] [rbp-45h]
  bool v8; // [rsp+34h] [rbp-44h]
  bool v9; // [rsp+35h] [rbp-43h]
  bool v10; // [rsp+36h] [rbp-42h]
  char v11; // [rsp+37h] [rbp-41h] BYREF
  bool v12; // [rsp+38h] [rbp-40h] BYREF
  bool v13; // [rsp+39h] [rbp-3Fh] BYREF
  BOOL v14; // [rsp+3Ch] [rbp-3Ch]
  BOOL v15; // [rsp+40h] [rbp-38h]
  LONG_PTR dwNewLong; // [rsp+48h] [rbp-30h] BYREF
  int v17; // [rsp+50h] [rbp-28h]
  int v18; // [rsp+54h] [rbp-24h]
  DWORD LastError; // [rsp+58h] [rbp-20h] BYREF
  __int64 (__fastcall *v20)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+60h] [rbp-18h]
  HWND hWnd; // [rsp+80h] [rbp+8h] BYREF
  struct SUBCLASS_HEADER *v22; // [rsp+88h] [rbp+10h] BYREF
  char v23; // [rsp+90h] [rbp+18h] BYREF

  v23 = a3;
  v22 = a2;
  hWnd = a1;
  v4 = 1;
  v14 = *((_DWORD *)a2 + 3) == GetCurrentThreadId();
  v4 = v14;
  v11 = IsWindowOnCurrentThread(hWnd);
  SHCoreTelemetry::DetachSubclassHeader<HWND__ * &,SUBCLASS_HEADER * &,bool &,bool &,bool>(
    (unsigned int)&hWnd,
    (unsigned int)&v22,
    (unsigned int)&v23,
    (unsigned int)&v4,
    (__int64)&v11);
  if ( !v23 && hWnd )
  {
    if ( *(_DWORD *)v22 <= 1u
      && !*((_QWORD *)v22 + 2)
      && *((_DWORD *)v22 + 3) == GetCurrentThreadId()
      && (char *)GetWindowProc(hWnd) == (char *)MasterSubclassProc )
    {
      dwNewLong = *((_QWORD *)v22 + 5);
      SubclassHeader = GetSubclassHeader(hWnd);
      v7 = v22 != SubclassHeader || !*(_DWORD *)v22;
      v6 = v7;
      v8 = !dwNewLong
        || (__int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64))dwNewLong == MasterSubclassProc;
      v5 = v8;
      SHCoreTelemetry::SHSetWindowSubclassDetachAttempt<HWND__ * &,bool const &,unsigned int &,bool const &,__int64 (*const &)(HWND__ *,unsigned int,unsigned __int64,__int64)>(
        (unsigned int)&hWnd,
        (unsigned int)&v6,
        (_DWORD)v22,
        (unsigned int)&v5,
        (__int64)&dwNewLong);
      if ( v6 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v17 = 0;
      }
      else
      {
        v17 = 1;
      }
      if ( v5 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v18 = 0;
      }
      else
      {
        v18 = 1;
      }
      v4 = 0;
      if ( !v5 && !v6 )
      {
        SetLastError(0);
        v20 = (__int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64))SetWindowLongPtrW(
                                                                                       hWnd,
                                                                                       -4,
                                                                                       dwNewLong);
        v9 = v20 != MasterSubclassProc;
        v13 = v20 != MasterSubclassProc;
        v10 = v20 != 0;
        v12 = v20 != 0;
        v15 = v20 == MasterSubclassProc;
        v4 = v20 == MasterSubclassProc;
        LastError = GetLastError();
        SHCoreTelemetry::SHSetWindowSubclassDetachResult<HWND__ * &,unsigned long,bool &,bool const &,bool const &>(
          (unsigned int)&hWnd,
          (unsigned int)&LastError,
          (unsigned int)&v4,
          (unsigned int)&v13,
          (__int64)&v12);
      }
    }
    else
    {
      v4 = 0;
    }
  }
  if ( v4 )
    FreeSubclassHeader(hWnd, v22);
}

```

## disassembly

```asm
0x18008d538  mov     [rsp+arg_10], r8b
0x18008d53d  mov     [rsp+arg_8], rdx
0x18008d542  mov     [rsp+hWnd], rcx
0x18008d547  sub     rsp, 78h
0x18008d54b  mov     [rsp+78h+var_48], 1
0x18008d550  call    cs:__imp_GetCurrentThreadId
0x18008d556  mov     rcx, [rsp+78h+arg_8]
0x18008d55e  cmp     [rcx+0Ch], eax
0x18008d561  jnz     short loc_18008D56D
0x18008d563  mov     [rsp+78h+var_3C], 1
0x18008d56b  jmp     short loc_18008D575
0x18008d56d  mov     [rsp+78h+var_3C], 0
0x18008d575  mov     al, byte ptr [rsp+78h+var_3C]
0x18008d579  mov     [rsp+78h+var_48], al
0x18008d57d  mov     rcx, [rsp+78h+hWnd]; hWnd
0x18008d585  call    ?IsWindowOnCurrentThread@@YA_NPEAUHWND__@@@Z; IsWindowOnCurrentThread(HWND__ *)
0x18008d58a  mov     [rsp+78h+var_41], al
0x18008d58e  lea     rax, [rsp+78h+var_41]
0x18008d593  mov     [rsp+78h+var_58], rax
0x18008d598  lea     r9, [rsp+78h+var_48]
0x18008d59d  lea     r8, [rsp+78h+arg_10]
0x18008d5a5  lea     rdx, [rsp+78h+arg_8]
0x18008d5ad  lea     rcx, [rsp+78h+hWnd]
0x18008d5b5  call    ??$DetachSubclassHeader@AEAPEAUHWND__@@AEAPEAUSUBCLASS_HEADER@@AEA_NAEA_N_N@SHCoreTelemetry@@SAXAEAPEAUHWND__@@AEAPEAUSUBCLASS_HEADER@@AEA_N2$$QEA_N@Z; SHCoreTelemetry::DetachSubclassHeader<HWND__ * &,SUBCLASS_HEADER * &,bool &,bool &,bool>(HWND__ * &,SUBCLASS_HEADER * &,bool &,bool &,bool &&)
0x18008d5ba  nop
0x18008d5bb  movzx   eax, [rsp+78h+arg_10]
0x18008d5c3  test    eax, eax
0x18008d5c5  jnz     loc_18008D7FD
0x18008d5cb  cmp     [rsp+78h+hWnd], 0
0x18008d5d4  jz      loc_18008D7FD
0x18008d5da  mov     rax, [rsp+78h+arg_8]
0x18008d5e2  cmp     dword ptr [rax], 1
0x18008d5e5  ja      loc_18008D7F8
0x18008d5eb  mov     rax, [rsp+78h+arg_8]
0x18008d5f3  cmp     qword ptr [rax+10h], 0
0x18008d5f8  jnz     loc_18008D7F8
0x18008d5fe  call    cs:__imp_GetCurrentThreadId
0x18008d604  mov     rcx, [rsp+78h+arg_8]
0x18008d60c  cmp     [rcx+0Ch], eax
0x18008d60f  jnz     loc_18008D7F8
0x18008d615  mov     rcx, [rsp+78h+hWnd]; HWND
0x18008d61d  call    ?GetWindowProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0@Z; GetWindowProc(HWND__ *)
0x18008d622  lea     rcx, ?MasterSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z; MasterSubclassProc(HWND__ *,uint,unsigned __int64,__int64)
0x18008d629  cmp     rax, rcx
0x18008d62c  jnz     loc_18008D7F8
0x18008d632  mov     eax, 18h
0x18008d637  imul    rax, 0
0x18008d63b  mov     rcx, [rsp+78h+arg_8]
0x18008d643  mov     rax, [rcx+rax+28h]
0x18008d648  mov     [rsp+78h+dwNewLong], rax
0x18008d64d  mov     rcx, [rsp+78h+hWnd]; HWND
0x18008d655  call    ?GetSubclassHeader@@YAPEAUSUBCLASS_HEADER@@PEAUHWND__@@@Z; GetSubclassHeader(HWND__ *)
0x18008d65a  cmp     [rsp+78h+arg_8], rax
0x18008d662  jnz     short loc_18008D678
0x18008d664  mov     rax, [rsp+78h+arg_8]
0x18008d66c  cmp     dword ptr [rax], 0
0x18008d66f  jz      short loc_18008D678
0x18008d671  mov     [rsp+78h+var_45], 0
0x18008d676  jmp     short loc_18008D67D
0x18008d678  mov     [rsp+78h+var_45], 1
0x18008d67d  mov     al, [rsp+78h+var_45]
0x18008d681  mov     [rsp+78h+var_46], al
0x18008d685  cmp     [rsp+78h+dwNewLong], 0
0x18008d68b  jz      short loc_18008D6A2
0x18008d68d  lea     rax, ?MasterSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z; MasterSubclassProc(HWND__ *,uint,unsigned __int64,__int64)
0x18008d694  cmp     [rsp+78h+dwNewLong], rax
0x18008d699  jz      short loc_18008D6A2
0x18008d69b  mov     [rsp+78h+var_44], 0
0x18008d6a0  jmp     short loc_18008D6A7
0x18008d6a2  mov     [rsp+78h+var_44], 1
0x18008d6a7  mov     al, [rsp+78h+var_44]
0x18008d6ab  mov     [rsp+78h+var_47], al
0x18008d6af  mov     rax, [rsp+78h+arg_8]
0x18008d6b7  lea     rcx, [rsp+78h+dwNewLong]
0x18008d6bc  mov     [rsp+78h+var_58], rcx
0x18008d6c1  lea     r9, [rsp+78h+var_47]
0x18008d6c6  mov     r8, rax
0x18008d6c9  lea     rdx, [rsp+78h+var_46]
0x18008d6ce  lea     rcx, [rsp+78h+hWnd]
0x18008d6d6  call    ??$SHSetWindowSubclassDetachAttempt@AEAPEAUHWND__@@AEB_NAEAIAEB_NAEBQ6A_JPEAU1@I_K_J@Z@SHCoreTelemetry@@SAXAEAPEAUHWND__@@AEB_NAEAI1AEBQ6A_JPEAU1@I_K_J@Z@Z; SHCoreTelemetry::SHSetWindowSubclassDetachAttempt<HWND__ * &,bool const &,uint &,bool const &,__int64 (*const &)(HWND__ *,uint,unsigned __int64,__int64)>(HWND__ * &,bool const &,uint &,bool const &,__int64 (*const &)(HWND__ *,uint,unsigned __int64,__int64))
0x18008d6db  movzx   eax, [rsp+78h+var_46]
0x18008d6e0  test    eax, eax
0x18008d6e2  jz      short loc_18008D6F3
0x18008d6e4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d6e9  mov     [rsp+78h+var_28], 0
0x18008d6f1  jmp     short loc_18008D6FB
0x18008d6f3  mov     [rsp+78h+var_28], 1
0x18008d6fb  movzx   eax, [rsp+78h+var_47]
0x18008d700  test    eax, eax
0x18008d702  jz      short loc_18008D713
0x18008d704  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d709  mov     [rsp+78h+var_24], 0
0x18008d711  jmp     short loc_18008D71B
0x18008d713  mov     [rsp+78h+var_24], 1
0x18008d71b  mov     [rsp+78h+var_48], 0
0x18008d720  movzx   eax, [rsp+78h+var_47]
0x18008d725  test    eax, eax
0x18008d727  jnz     loc_18008D7F6
0x18008d72d  movzx   eax, [rsp+78h+var_46]
0x18008d732  test    eax, eax
0x18008d734  jnz     loc_18008D7F6
0x18008d73a  xor     ecx, ecx; dwErrCode
0x18008d73c  call    cs:__imp_SetLastError
0x18008d742  mov     r8, [rsp+78h+dwNewLong]; dwNewLong
0x18008d747  mov     edx, 0FFFFFFFCh; nIndex
0x18008d74c  mov     rcx, [rsp+78h+hWnd]; hWnd
0x18008d754  call    cs:__imp_SetWindowLongPtrW
0x18008d75a  mov     [rsp+78h+var_18], rax
0x18008d75f  lea     rax, ?MasterSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z; MasterSubclassProc(HWND__ *,uint,unsigned __int64,__int64)
0x18008d766  cmp     [rsp+78h+var_18], rax
0x18008d76b  jz      short loc_18008D774
0x18008d76d  mov     [rsp+78h+var_43], 1
0x18008d772  jmp     short loc_18008D779
0x18008d774  mov     [rsp+78h+var_43], 0
0x18008d779  mov     al, [rsp+78h+var_43]
0x18008d77d  mov     [rsp+78h+var_3F], al
0x18008d781  cmp     [rsp+78h+var_18], 0
0x18008d787  jz      short loc_18008D790
0x18008d789  mov     [rsp+78h+var_42], 1
0x18008d78e  jmp     short loc_18008D795
0x18008d790  mov     [rsp+78h+var_42], 0
0x18008d795  mov     al, [rsp+78h+var_42]
0x18008d799  mov     [rsp+78h+var_40], al
0x18008d79d  lea     rax, ?MasterSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z; MasterSubclassProc(HWND__ *,uint,unsigned __int64,__int64)
0x18008d7a4  cmp     [rsp+78h+var_18], rax
0x18008d7a9  jnz     short loc_18008D7B5
0x18008d7ab  mov     [rsp+78h+var_38], 1
0x18008d7b3  jmp     short loc_18008D7BD
0x18008d7b5  mov     [rsp+78h+var_38], 0
0x18008d7bd  mov     al, byte ptr [rsp+78h+var_38]
0x18008d7c1  mov     [rsp+78h+var_48], al
0x18008d7c5  call    cs:__imp_GetLastError
0x18008d7cb  mov     [rsp+78h+var_20], eax
0x18008d7cf  lea     rax, [rsp+78h+var_40]
0x18008d7d4  mov     [rsp+78h+var_58], rax
0x18008d7d9  lea     r9, [rsp+78h+var_3F]
0x18008d7de  lea     r8, [rsp+78h+var_48]
0x18008d7e3  lea     rdx, [rsp+78h+var_20]
0x18008d7e8  lea     rcx, [rsp+78h+hWnd]
0x18008d7f0  call    ??$SHSetWindowSubclassDetachResult@AEAPEAUHWND__@@KAEA_NAEB_NAEB_N@SHCoreTelemetry@@SAXAEAPEAUHWND__@@$$QEAKAEA_NAEB_N3@Z; SHCoreTelemetry::SHSetWindowSubclassDetachResult<HWND__ * &,ulong,bool &,bool const &,bool const &>(HWND__ * &,ulong &&,bool &,bool const &,bool const &)
0x18008d7f5  nop
0x18008d7f6  jmp     short loc_18008D7FD
0x18008d7f8  mov     [rsp+78h+var_48], 0
0x18008d7fd  movzx   eax, [rsp+78h+var_48]
0x18008d802  test    eax, eax
0x18008d804  jz      short loc_18008D81C
0x18008d806  mov     rdx, [rsp+78h+arg_8]; struct SUBCLASS_HEADER *
0x18008d80e  mov     rcx, [rsp+78h+hWnd]; HWND
0x18008d816  call    ?FreeSubclassHeader@@YAXPEAUHWND__@@PEAUSUBCLASS_HEADER@@@Z; FreeSubclassHeader(HWND__ *,SUBCLASS_HEADER *)
0x18008d81b  nop
0x18008d81c  add     rsp, 78h
0x18008d820  retn
```
