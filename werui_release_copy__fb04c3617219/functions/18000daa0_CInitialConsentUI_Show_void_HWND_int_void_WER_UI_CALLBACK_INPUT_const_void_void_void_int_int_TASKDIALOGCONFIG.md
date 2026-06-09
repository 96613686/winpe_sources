# CInitialConsentUI::Show(void *,HWND__ *,int (*)(void *,_WER_UI_CALLBACK_INPUT * const),void *,void *,void *,int,int,_TASKDIALOGCONFIG *)

- ea: `0x18000daa0`
- end: `0x18000dd39`
- name: `?Show@CInitialConsentUI@@QEAA?AW4USER_SELECTION@@PEAXPEAUHWND__@@P6AH0QEAU_WER_UI_CALLBACK_INPUT@@@Z000HHPEAU_TASKDIALOGCONFIG@@@Z`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180006550`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180008fb8`
- `0x18000983c`
- `0x18000c13c`
- `0x18000daa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000dc25`
- `KERNEL32!GetLastError` at `0x18000dca2`
- `KERNEL32!GetLastError` at `0x18000dc25`
- `KERNEL32!GetLastError` at `0x18000dca2`
- `KERNEL32!WaitForSingleObject` at `0x18000db55`
- `KERNEL32!WaitForSingleObject` at `0x18000db55`
- `KERNEL32!CreateThread` at `0x18000dc84`
- `KERNEL32!CreateThread` at `0x18000dc84`
- `KERNEL32!CreateEventW` at `0x18000dc08`
- `KERNEL32!CreateEventW` at `0x18000dc08`

## pseudocode

```c
__int64 __fastcall CInitialConsentUI::Show(
        __int64 a1,
        void *a2,
        __int64 a3,
        int (*a4)(void *, struct _WER_UI_CALLBACK_INPUT *const),
        void *a5,
        HANDLE hHandle,
        __int64 a7,
        int a8,
        int a9,
        _OWORD *a10)
{
  _OWORD *v12; // rbx
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  HANDLE v16; // rcx
  __int64 v17; // rax
  void **v18; // rsi
  bool v19; // zf
  int v20; // eax
  HANDLE EventW; // rax
  DWORD LastError; // eax
  HANDLE v23; // rax
  int v24; // r9d
  void *v25; // rcx
  DWORD v26; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  void *v29[2]; // [rsp+30h] [rbp-18h] BYREF
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF

  ThreadId = 0;
  *(_OWORD *)v29 = 0;
  if ( a2 )
  {
    v12 = a10;
    if ( a10 )
    {
      v13 = CUIDlgBase::Initialize((CUIDlgBase *)a1, a2, a4, a5);
      if ( v13 >= 0 )
      {
        v16 = hHandle;
        v17 = a7;
        *(_QWORD *)(a1 + 320) = hHandle;
        *(_QWORD *)(a1 + 328) = v17;
        *(_QWORD *)(a1 + 256) = a3;
        v18 = (void **)(a1 + 360);
        v19 = WaitForSingleObject(v16, 0) == 0;
        *(_DWORD *)(a1 + 344) = a8;
        v20 = a9;
        *(_DWORD *)(a1 + 336) = v19;
        *(_DWORD *)(a1 + 532) = v20;
        *(_OWORD *)(a1 + 372) = *v12;
        *(_OWORD *)(a1 + 388) = v12[1];
        *(_OWORD *)(a1 + 404) = v12[2];
        *(_OWORD *)(a1 + 420) = v12[3];
        *(_OWORD *)(a1 + 436) = v12[4];
        *(_OWORD *)(a1 + 452) = v12[5];
        *(_OWORD *)(a1 + 468) = v12[6];
        *(_OWORD *)(a1 + 484) = v12[7];
        *(_OWORD *)(a1 + 500) = v12[8];
        *(_OWORD *)(a1 + 516) = v12[9];
        EventW = CreateEventW(0, 1, 0, 0);
        tlx::unique_any<tlx::file_handle_traits>::reset(a1 + 360, EventW);
        if ( *v18 == (void *)-1LL || (char *)*v18 + 1 == (void *)1 )
        {
          LastError = GetLastError();
          v13 = ERROR_HR_FROM_WIN32(LastError);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return *(unsigned int *)(a1 + 368);
          v15 = 29;
        }
        else
        {
          v23 = CreateThread(0, 0, CInitialConsentUI::Static_InitialDlgThreadRoutine, (LPVOID)a1, 0, &ThreadId);
          tlx::unique_any<tlx::file_handle_traits>::reset(a1 + 352, v23);
          v25 = *(void **)(a1 + 352);
          if ( (unsigned __int64)v25 + 1 > 1 )
          {
            v29[0] = *v18;
            v29[1] = v25;
            UtilMsgWaitForMultipleObjects((const unsigned __int16 *)v25, 2u, v29, v24, dwCreationFlags);
            return *(unsigned int *)(a1 + 368);
          }
          v26 = GetLastError();
          v13 = ERROR_HR_FROM_WIN32(v26);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return *(unsigned int *)(a1 + 368);
          v15 = 30;
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return *(unsigned int *)(a1 + 368);
        v15 = 28;
      }
      WPP_SF_d(v14[2], v15, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids, (unsigned int)v13);
      return *(unsigned int *)(a1 + 368);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids);
  return 11;
}

```

## disassembly

```asm
0x18000daa0  mov     [rsp+arg_0], rbx
0x18000daa5  mov     [rsp+arg_10], rsi
0x18000daaa  push    rdi
0x18000daab  sub     rsp, 40h
0x18000daaf  mov     [rsp+48h+ThreadId], 0
0x18000dab7  xorps   xmm0, xmm0
0x18000daba  mov     rax, r9
0x18000dabd  mov     rsi, r8
0x18000dac0  mov     rdi, rcx
0x18000dac3  movups  xmmword ptr [rsp+48h+var_18], xmm0
0x18000dac8  test    rdx, rdx
0x18000dacb  jz      loc_18000DCF6
0x18000dad1  mov     rbx, [rsp+48h+arg_48]
0x18000dad9  test    rbx, rbx
0x18000dadc  jz      loc_18000DCF6
0x18000dae2  mov     r9, [rsp+48h+arg_20]; void *
0x18000dae7  mov     r8, rax; int (*)(void *, struct _WER_UI_CALLBACK_INPUT *const)
0x18000daea  call    ?Initialize@CUIDlgBase@@IEAAJPEAXP6AH0QEAU_WER_UI_CALLBACK_INPUT@@@Z0@Z; CUIDlgBase::Initialize(void *,int (*)(void *,_WER_UI_CALLBACK_INPUT * const),void *)
0x18000daef  test    eax, eax
0x18000daf1  jns     short loc_18000DB31
0x18000daf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dafa  lea     rdx, WPP_GLOBAL_Control
0x18000db01  cmp     rcx, rdx
0x18000db04  jz      loc_18000DCEE
0x18000db0a  test    byte ptr [rcx+1Ch], 1
0x18000db0e  jz      loc_18000DCEE
0x18000db14  mov     edx, 1Ch
0x18000db19  mov     rcx, [rcx+10h]
0x18000db1d  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000db24  mov     r9d, eax
0x18000db27  call    WPP_SF_d
0x18000db2c  jmp     loc_18000DCEE
0x18000db31  mov     rcx, [rsp+48h+hHandle]; hHandle
0x18000db36  xor     edx, edx; dwMilliseconds
0x18000db38  mov     rax, [rsp+48h+arg_30]
0x18000db40  mov     [rdi+140h], rcx
0x18000db47  mov     [rdi+148h], rax
0x18000db4e  mov     [rdi+100h], rsi
0x18000db55  call    cs:__imp_WaitForSingleObject
0x18000db5b  xor     ecx, ecx
0x18000db5d  lea     rsi, [rdi+168h]
0x18000db64  test    eax, eax
0x18000db66  mov     eax, [rsp+48h+arg_38]
0x18000db6d  mov     [rdi+158h], eax
0x18000db73  mov     eax, [rsp+48h+arg_40]
0x18000db7a  setz    cl
0x18000db7d  mov     [rdi+150h], ecx
0x18000db83  xor     r9d, r9d; lpName
0x18000db86  mov     [rdi+214h], eax
0x18000db8c  xor     r8d, r8d; bInitialState
0x18000db8f  movups  xmm0, xmmword ptr [rbx]
0x18000db92  xor     ecx, ecx; lpEventAttributes
0x18000db94  lea     edx, [r9+1]; bManualReset
0x18000db98  movups  xmmword ptr [rdi+174h], xmm0
0x18000db9f  movups  xmm1, xmmword ptr [rbx+10h]
0x18000dba3  movups  xmmword ptr [rdi+184h], xmm1
0x18000dbaa  movups  xmm0, xmmword ptr [rbx+20h]
0x18000dbae  movups  xmmword ptr [rdi+194h], xmm0
0x18000dbb5  movups  xmm1, xmmword ptr [rbx+30h]
0x18000dbb9  movups  xmmword ptr [rdi+1A4h], xmm1
0x18000dbc0  movups  xmm0, xmmword ptr [rbx+40h]
0x18000dbc4  movups  xmmword ptr [rdi+1B4h], xmm0
0x18000dbcb  movups  xmm1, xmmword ptr [rbx+50h]
0x18000dbcf  movups  xmmword ptr [rdi+1C4h], xmm1
0x18000dbd6  movups  xmm0, xmmword ptr [rbx+60h]
0x18000dbda  movups  xmmword ptr [rdi+1D4h], xmm0
0x18000dbe1  movups  xmm1, xmmword ptr [rbx+70h]
0x18000dbe5  movups  xmmword ptr [rdi+1E4h], xmm1
0x18000dbec  movups  xmm0, xmmword ptr [rbx+80h]
0x18000dbf3  movups  xmmword ptr [rdi+1F4h], xmm0
0x18000dbfa  movups  xmm1, xmmword ptr [rbx+90h]
0x18000dc01  movups  xmmword ptr [rdi+204h], xmm1
0x18000dc08  call    cs:__imp_CreateEventW
0x18000dc0e  mov     rdx, rax
0x18000dc11  mov     rcx, rsi
0x18000dc14  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000dc19  mov     rax, [rsi]
0x18000dc1c  inc     rax
0x18000dc1f  cmp     rax, 1
0x18000dc23  ja      short loc_18000DC5D
0x18000dc25  call    cs:__imp_GetLastError
0x18000dc2b  mov     ecx, eax; unsigned int
0x18000dc2d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000dc32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc39  lea     rdx, WPP_GLOBAL_Control
0x18000dc40  cmp     rcx, rdx
0x18000dc43  jz      loc_18000DCEE
0x18000dc49  test    byte ptr [rcx+1Ch], 1
0x18000dc4d  jz      loc_18000DCEE
0x18000dc53  mov     edx, 1Dh
0x18000dc58  jmp     loc_18000DB19
0x18000dc5d  lea     rax, [rsp+48h+ThreadId]
0x18000dc62  mov     r9, rdi; lpParameter
0x18000dc65  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18000dc6a  lea     r8, ?Static_InitialDlgThreadRoutine@CInitialConsentUI@@CAKPEAX@Z; lpStartAddress
0x18000dc71  xor     edx, edx; dwStackSize
0x18000dc73  mov     [rsp+48h+dwCreationFlags], 0; unsigned int
0x18000dc7b  xor     ecx, ecx; lpThreadAttributes
0x18000dc7d  lea     rbx, [rdi+160h]
0x18000dc84  call    cs:__imp_CreateThread
0x18000dc8a  mov     rdx, rax
0x18000dc8d  mov     rcx, rbx
0x18000dc90  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000dc95  mov     rcx, [rbx]; unsigned __int16 *
0x18000dc98  lea     rax, [rcx+1]
0x18000dc9c  cmp     rax, 1
0x18000dca0  ja      short loc_18000DCD2
0x18000dca2  call    cs:__imp_GetLastError
0x18000dca8  mov     ecx, eax; unsigned int
0x18000dcaa  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000dcaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcb6  lea     rdx, WPP_GLOBAL_Control
0x18000dcbd  cmp     rcx, rdx
0x18000dcc0  jz      short loc_18000DCEE
0x18000dcc2  test    byte ptr [rcx+1Ch], 1
0x18000dcc6  jz      short loc_18000DCEE
0x18000dcc8  mov     edx, 1Eh
0x18000dccd  jmp     loc_18000DB19
0x18000dcd2  mov     rax, [rsi]
0x18000dcd5  lea     r8, [rsp+48h+var_18]; void **
0x18000dcda  mov     edx, 2; unsigned int
0x18000dcdf  mov     [rsp+48h+var_18], rax
0x18000dce4  mov     [rsp+48h+var_18+8], rcx
0x18000dce9  call    ?UtilMsgWaitForMultipleObjects@@YAKPEBGKQEAPEAXHK@Z; UtilMsgWaitForMultipleObjects(ushort const *,ulong,void * * const,int,ulong)
0x18000dcee  mov     eax, [rdi+170h]
0x18000dcf4  jmp     short loc_18000DD29
0x18000dcf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcfd  lea     rdx, WPP_GLOBAL_Control
0x18000dd04  cmp     rcx, rdx
0x18000dd07  jz      short loc_18000DD24
0x18000dd09  test    byte ptr [rcx+1Ch], 1
0x18000dd0d  jz      short loc_18000DD24
0x18000dd0f  mov     rcx, [rcx+10h]
0x18000dd13  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000dd1a  mov     edx, 1Bh
0x18000dd1f  call    WPP_SF_
0x18000dd24  mov     eax, 0Bh
0x18000dd29  mov     rbx, [rsp+48h+arg_0]
0x18000dd2e  mov     rsi, [rsp+48h+arg_10]
0x18000dd33  add     rsp, 40h
0x18000dd37  pop     rdi
0x18000dd38  retn
```
