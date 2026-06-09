# RunInteractiveUIThread(void *)

- ea: `0x180032890`
- end: `0x180032a60`
- name: `?RunInteractiveUIThread@@YAIPEAX@Z`
- size: `464`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x180031fe4`
- `0x18003216c`
- `0x180032890`
- `0x180032a68`
- `0x180032bcc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180032a43`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180032a43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032a13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032a13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032a35`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180032937`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180032937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032997`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800328ac`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800328ac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032a3b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032a4e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032a3b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032a4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RunInteractiveUIThread(HANDLE *a1)
{
  _QWORD *v2; // rsi
  HRESULT v3; // ebx
  HANDLE v4; // r8
  HANDLE v5; // rdx
  HANDLE v6; // rcx
  DWORD v7; // eax
  DWORD LastError; // eax
  HANDLE Handles[7]; // [rsp+30h] [rbp-38h] BYREF

  v2 = 0;
  *(_OWORD *)Handles = 0;
  v3 = CoInitializeEx(0, 4u);
  if ( a1 )
  {
    if ( a1[7] )
    {
      v2 = a1[7];
      v4 = a1[6];
      v5 = a1[5];
      v6 = a1[3];
      v2[10] = a1[2];
      v2[12] = v6;
      v2[11] = v5;
      v2[13] = v4;
      if ( !CWlanSSODialogSink::StartSubscribeWnfUiRequest((CWlanSSODialogSink *)v2) )
      {
        Handles[0] = a1[2];
        Handles[1] = a1[1];
        *((_DWORD *)v2 + 16) = 1;
        while ( 1 )
        {
          v7 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
          if ( v7 )
          {
            if ( v7 == 1 )
              goto LABEL_19;
            if ( v7 != 128 )
              break;
          }
          if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_1d0b8d757678329d0edebcebbe5bfb61_Traceguids);
          }
          CWlanSSODialogSink::BatchProcessUIRequests((CWlanSSODialogSink *)v2, (int *)*a1);
        }
        if ( v7 != 129 )
        {
          if ( v7 == -1 )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                12,
                WPP_1d0b8d757678329d0edebcebbe5bfb61_Traceguids,
                LastError);
            }
          }
          goto LABEL_24;
        }
LABEL_19:
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_1d0b8d757678329d0edebcebbe5bfb61_Traceguids);
        }
        *((_DWORD *)v2 + 16) = 0;
LABEL_24:
        CWlanSSODialogSink::StopSubscribeWnfUiRequest((CWlanSSODialogSink *)v2);
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1[6] + 48));
  *((_DWORD *)v2 + 16) = 0;
  while ( (unsigned __int8)CLockedUIRequestQueue<CInteractiveUIRequest *>::Dequeue(a1[6]) )
    ;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1[6] + 48));
  CoUninitialize();
  _o__endthreadex(0);
  if ( v3 >= 0 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180032890  push    rbx
0x180032892  push    rsi
0x180032893  push    rdi
0x180032894  push    r12
0x180032896  sub     rsp, 48h
0x18003289a  mov     rdi, rcx
0x18003289d  xor     esi, esi
0x18003289f  xorps   xmm0, xmm0
0x1800328a2  movups  xmmword ptr [rsp+68h+Handles], xmm0
0x1800328a7  lea     edx, [rsi+4]; dwCoInit
0x1800328aa  xor     ecx, ecx; pvReserved
0x1800328ac  call    cs:__imp_CoInitializeEx
0x1800328b2  mov     ebx, eax
0x1800328b4  mov     [rsp+68h+arg_0], eax
0x1800328b8  test    rdi, rdi
0x1800328bb  jz      loc_180032A0B
0x1800328c1  cmp     [rdi+38h], rsi
0x1800328c5  jz      loc_180032A0B
0x1800328cb  mov     rsi, [rdi+38h]
0x1800328cf  mov     r8, [rdi+30h]
0x1800328d3  mov     rdx, [rdi+28h]
0x1800328d7  mov     rcx, [rdi+18h]
0x1800328db  mov     rax, [rdi+10h]
0x1800328df  mov     [rsi+50h], rax
0x1800328e3  mov     [rsi+60h], rcx
0x1800328e7  mov     [rsi+58h], rdx
0x1800328eb  mov     [rsi+68h], r8
0x1800328ef  mov     rcx, rsi; this
0x1800328f2  call    ?StartSubscribeWnfUiRequest@CWlanSSODialogSink@@QEAAKXZ; CWlanSSODialogSink::StartSubscribeWnfUiRequest(void)
0x1800328f7  test    eax, eax
0x1800328f9  jnz     loc_180032A0B
0x1800328ff  mov     rax, [rdi+10h]
0x180032903  mov     [rsp+68h+Handles], rax
0x180032908  mov     rax, [rdi+8]
0x18003290c  mov     [rsp+68h+Handles+8], rax
0x180032911  mov     dword ptr [rsi+40h], 1
0x180032918  lea     r12, WPP_GLOBAL_Control
0x18003291f  mov     [rsp+68h+bAlertable], 0; bAlertable
0x180032927  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18003292b  xor     r8d, r8d; bWaitAll
0x18003292e  lea     rdx, [rsp+68h+Handles]; lpHandles
0x180032933  lea     ecx, [r8+2]; nCount
0x180032937  call    cs:__imp_WaitForMultipleObjectsEx
0x18003293d  test    eax, eax
0x18003293f  jz      short loc_180032951
0x180032941  cmp     eax, 1
0x180032944  jz      loc_1800329CF
0x18003294a  cmp     eax, 80h
0x18003294f  jnz     short loc_18003298B
0x180032951  mov     rcx, cs:WPP_GLOBAL_Control
0x180032958  cmp     rcx, r12
0x18003295b  jz      short loc_18003297E
0x18003295d  cmp     byte ptr [rcx+69h], 3
0x180032961  jb      short loc_18003297E
0x180032963  test    byte ptr [rcx+6Ch], 2
0x180032967  jz      short loc_18003297E
0x180032969  mov     edx, 0Bh
0x18003296e  lea     r8, WPP_1d0b8d757678329d0edebcebbe5bfb61_Traceguids
0x180032975  mov     rcx, [rcx+60h]
0x180032979  call    WPP_SF_
0x18003297e  mov     rdx, [rdi]; int *
0x180032981  mov     rcx, rsi; this
0x180032984  call    ?BatchProcessUIRequests@CWlanSSODialogSink@@QEAAXPEAH@Z; CWlanSSODialogSink::BatchProcessUIRequests(int *)
0x180032989  jmp     short loc_18003291F
0x18003298b  cmp     eax, 81h
0x180032990  jz      short loc_1800329CF
0x180032992  cmp     eax, 0FFFFFFFFh
0x180032995  jnz     short loc_180032A03
0x180032997  call    cs:__imp_GetLastError
0x18003299d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329a4  cmp     rcx, r12
0x1800329a7  jz      short loc_180032A03
0x1800329a9  cmp     byte ptr [rcx+69h], 3
0x1800329ad  jb      short loc_180032A03
0x1800329af  test    byte ptr [rcx+6Ch], 2
0x1800329b3  jz      short loc_180032A03
0x1800329b5  mov     edx, 0Ch
0x1800329ba  mov     r9d, eax
0x1800329bd  lea     r8, WPP_1d0b8d757678329d0edebcebbe5bfb61_Traceguids
0x1800329c4  mov     rcx, [rcx+60h]
0x1800329c8  call    WPP_SF_d
0x1800329cd  jmp     short loc_180032A03
0x1800329cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329d6  cmp     rcx, r12
0x1800329d9  jz      short loc_1800329FC
0x1800329db  cmp     byte ptr [rcx+69h], 3
0x1800329df  jb      short loc_1800329FC
0x1800329e1  test    byte ptr [rcx+6Ch], 2
0x1800329e5  jz      short loc_1800329FC
0x1800329e7  mov     edx, 0Ah
0x1800329ec  lea     r8, WPP_1d0b8d757678329d0edebcebbe5bfb61_Traceguids
0x1800329f3  mov     rcx, [rcx+60h]
0x1800329f7  call    WPP_SF_
0x1800329fc  mov     dword ptr [rsi+40h], 0
0x180032a03  mov     rcx, rsi; this
0x180032a06  call    ?StopSubscribeWnfUiRequest@CWlanSSODialogSink@@QEAAXXZ; CWlanSSODialogSink::StopSubscribeWnfUiRequest(void)
0x180032a0b  mov     rcx, [rdi+30h]
0x180032a0f  add     rcx, 30h ; '0'; lpCriticalSection
0x180032a13  call    cs:__imp_EnterCriticalSection
0x180032a19  mov     dword ptr [rsi+40h], 0
0x180032a20  mov     rcx, [rdi+30h]
0x180032a24  call    ?Dequeue@?$CLockedUIRequestQueue@PEAVCInteractiveUIRequest@@@@QEAA_NXZ; CLockedUIRequestQueue<CInteractiveUIRequest *>::Dequeue(void)
0x180032a29  test    al, al
0x180032a2b  jnz     short loc_180032A20
0x180032a2d  mov     rcx, [rdi+30h]
0x180032a31  add     rcx, 30h ; '0'; lpCriticalSection
0x180032a35  call    cs:__imp_LeaveCriticalSection
0x180032a3b  call    cs:__imp_CoUninitialize
0x180032a41  xor     ecx, ecx
0x180032a43  call    cs:__imp__o__endthreadex
0x180032a49  nop
0x180032a4a  test    ebx, ebx
0x180032a4c  js      short loc_180032A54
0x180032a4e  call    cs:__imp_CoUninitialize
0x180032a54  xor     eax, eax
0x180032a56  add     rsp, 48h
0x180032a5a  pop     r12
0x180032a5c  pop     rdi
0x180032a5d  pop     rsi
0x180032a5e  pop     rbx
0x180032a5f  retn
```
