# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x1800445a0`
- end: `0x18004473a`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `410`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180043d38`
- `0x1800445a0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800445cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800445cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800445e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004466e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004472c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800445e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004466e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004472c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004465d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004465d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044693`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004464d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004464d`

## pseudocode

```c
__int64 __fastcall ServiceBase::_ServiceCtrlHandler(
        __int64 dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  unsigned int v7; // esi
  unsigned int v8; // ebx
  __int64 v10; // rax
  int v11; // eax
  SERVICE_STATUS_HANDLE v12; // rcx
  signed int v13; // ebx
  signed int LastError; // eax
  signed int v15; // eax

  v7 = dwControl;
  if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x10) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      dwControl,
      ServiceBaseServiceControlHandler,
      lpContext + 8,
      (unsigned int)dwControl);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
  if ( *((_DWORD *)lpContext + 32) )
    goto LABEL_4;
  switch ( v7 )
  {
    case 1u:
      goto LABEL_9;
    case 4u:
      goto LABEL_15;
    case 5u:
    case 0xFu:
LABEL_9:
      *((_DWORD *)lpContext + 32) = 1;
      if ( v7 == 15 || v7 == 5 )
        *((_DWORD *)lpContext + 33) = 1;
      ++*((_DWORD *)lpContext + 29);
      v10 = *(_QWORD *)lpContext;
      *((_DWORD *)lpContext + 25) = 3;
      v11 = (*(__int64 (__fastcall **)(char *))(v10 + 72))(lpContext);
      v12 = (SERVICE_STATUS_HANDLE)*((_QWORD *)lpContext + 9);
      *((_DWORD *)lpContext + 30) = v11;
      if ( SetServiceStatus(v12, (LPSERVICE_STATUS)(lpContext + 96)) )
      {
        v13 = 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
      }
      SetEvent(*((HANDLE *)lpContext + 10));
      goto LABEL_14;
  }
  if ( v7 >= 0x80 )
  {
    if ( v7 <= 0xFF )
    {
      v15 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, LPVOID))(*(_QWORD *)lpContext + 40LL))(
              lpContext,
              v7,
              dwEventType,
              lpEventData);
      goto LABEL_24;
    }
LABEL_15:
    LeaveCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
    return 0;
  }
  if ( !v7 )
    goto LABEL_15;
  v15 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, LPVOID))(*(_QWORD *)lpContext + 48LL))(
          lpContext,
          v7,
          dwEventType,
          lpEventData);
LABEL_24:
  v13 = v15;
  if ( v15 == -2147467263 )
  {
    if ( v7 != 32 )
    {
      v8 = 120;
      goto LABEL_5;
    }
    if ( *((_DWORD *)lpContext + 32) )
    {
LABEL_4:
      v8 = 1115;
LABEL_5:
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
      return v8;
    }
    goto LABEL_15;
  }
LABEL_14:
  if ( v13 >= 0 || v7 == 15 )
    goto LABEL_15;
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
  return (unsigned __int16)v13;
}

```

## disassembly

```asm
0x1800445a0  push    rbx
0x1800445a2  push    rbp
0x1800445a3  push    rsi
0x1800445a4  push    rdi
0x1800445a5  push    r14
0x1800445a7  sub     rsp, 30h
0x1800445ab  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 10h
0x1800445b2  mov     rdi, r9
0x1800445b5  mov     rbx, r8
0x1800445b8  mov     r14d, edx
0x1800445bb  mov     esi, ecx
0x1800445bd  jnz     loc_18004467B
0x1800445c3  lea     rbp, [rdi+88h]
0x1800445ca  mov     rcx, rbp; lpCriticalSection
0x1800445cd  call    cs:__imp_EnterCriticalSection
0x1800445d3  cmp     dword ptr [rdi+80h], 0
0x1800445da  jz      short loc_1800445F7
0x1800445dc  mov     ebx, 45Bh
0x1800445e1  mov     rcx, rbp; lpCriticalSection
0x1800445e4  call    cs:__imp_LeaveCriticalSection
0x1800445ea  mov     eax, ebx
0x1800445ec  add     rsp, 30h
0x1800445f0  pop     r14
0x1800445f2  pop     rdi
0x1800445f3  pop     rsi
0x1800445f4  pop     rbp
0x1800445f5  pop     rbx
0x1800445f6  retn
0x1800445f7  mov     eax, esi
0x1800445f9  sub     eax, 1
0x1800445fc  jz      short loc_18004460C
0x1800445fe  sub     eax, 3
0x180044601  jz      short loc_18004466B
0x180044603  sub     eax, 1
0x180044606  jnz     loc_1800446AA
0x18004460c  mov     eax, 1
0x180044611  mov     [rdi+80h], eax
0x180044617  cmp     esi, 0Fh
0x18004461a  jz      loc_180044715
0x180044620  cmp     esi, 5
0x180044623  jz      loc_180044715
0x180044629  add     [rdi+74h], eax
0x18004462c  mov     rcx, rdi
0x18004462f  mov     rax, [rdi]
0x180044632  mov     dword ptr [rdi+64h], 3
0x180044639  mov     rax, [rax+48h]
0x18004463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044642  mov     rcx, [rdi+48h]; hServiceStatus
0x180044646  lea     rdx, [rdi+60h]; lpServiceStatus
0x18004464a  mov     [rdi+78h], eax
0x18004464d  call    cs:__imp_SetServiceStatus
0x180044653  test    eax, eax
0x180044655  jz      short loc_180044693
0x180044657  xor     ebx, ebx
0x180044659  mov     rcx, [rdi+50h]; hEvent
0x18004465d  call    cs:__imp_SetEvent
0x180044663  test    ebx, ebx
0x180044665  js      loc_180044720
0x18004466b  mov     rcx, rbp; lpCriticalSection
0x18004466e  call    cs:__imp_LeaveCriticalSection
0x180044674  xor     eax, eax
0x180044676  jmp     loc_1800445EC
0x18004467b  lea     r8, [r9+8]
0x18004467f  mov     r9d, esi
0x180044682  lea     rdx, ServiceBaseServiceControlHandler
0x180044689  call    McTemplateU0zq_EventWriteTransfer
0x18004468e  jmp     loc_1800445C3
0x180044693  call    cs:__imp_GetLastError
0x180044699  mov     ebx, eax
0x18004469b  test    eax, eax
0x18004469d  jle     short loc_180044659
0x18004469f  movzx   ebx, ax
0x1800446a2  or      ebx, 80070000h
0x1800446a8  jmp     short loc_180044659
0x1800446aa  cmp     eax, 0Ah
0x1800446ad  jz      loc_18004460C
0x1800446b3  cmp     esi, 80h
0x1800446b9  jb      short loc_1800446CC
0x1800446bb  cmp     esi, 0FFh
0x1800446c1  ja      short loc_18004466B
0x1800446c3  mov     rax, [rdi]
0x1800446c6  mov     rax, [rax+28h]
0x1800446ca  jmp     short loc_1800446D7
0x1800446cc  test    esi, esi
0x1800446ce  jz      short loc_18004466B
0x1800446d0  mov     rax, [rdi]
0x1800446d3  mov     rax, [rax+30h]
0x1800446d7  mov     r9, rbx
0x1800446da  mov     r8d, r14d
0x1800446dd  mov     edx, esi
0x1800446df  mov     rcx, rdi
0x1800446e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446e7  mov     ebx, eax
0x1800446e9  cmp     eax, 80004001h
0x1800446ee  jnz     loc_180044663
0x1800446f4  cmp     esi, 20h ; ' '
0x1800446f7  jnz     short loc_18004470B
0x1800446f9  cmp     dword ptr [rdi+80h], 0
0x180044700  jz      loc_18004466B
0x180044706  jmp     loc_1800445DC
0x18004470b  mov     ebx, 78h ; 'x'
0x180044710  jmp     loc_1800445E1
0x180044715  mov     [rdi+84h], eax
0x18004471b  jmp     loc_180044629
0x180044720  cmp     esi, 0Fh
0x180044723  jz      loc_18004466B
0x180044729  mov     rcx, rbp; lpCriticalSection
0x18004472c  call    cs:__imp_LeaveCriticalSection
0x180044732  movzx   eax, bx
0x180044735  jmp     loc_1800445EC
```
