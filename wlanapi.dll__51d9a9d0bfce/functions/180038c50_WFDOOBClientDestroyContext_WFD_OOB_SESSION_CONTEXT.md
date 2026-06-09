# WFDOOBClientDestroyContext(_WFD_OOB_SESSION_CONTEXT *)

- ea: `0x180038c50`
- end: `0x180038df9`
- name: `?WFDOOBClientDestroyContext@@YAKPEAU_WFD_OOB_SESSION_CONTEXT@@@Z`
- size: `425`
- prototype: `unsigned int __fastcall(struct _WFD_OOB_SESSION_CONTEXT *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180027ac0`
- `0x180038938`

## callees

- `0x18000349c`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x1800185f0`
- `0x180038c50`
- `0x180038f20`
- `0x180038fa8`
- `0x180050f44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038d93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038d5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038d5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038d78`

## pseudocode

```c
__int64 __fastcall WFDOOBClientDestroyContext(struct _WFD_OOB_SESSION_CONTEXT *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  unsigned int v4; // eax
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids);
  }
  v2 = WFDOobHelperRegisterForNotification(0, a1);
  v3 = v2;
  if ( v2
    && WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v2);
  }
  if ( *((_DWORD *)a1 + 17) )
  {
    v4 = WFDOobHelperSetPCDiscoverable(0, a1);
    v3 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v4);
      }
    }
  }
  v5 = (void *)*((_QWORD *)a1 + 115);
  if ( v5 )
  {
    WFDCloseSessionLib(v5);
    *((_QWORD *)a1 + 115) = 0;
  }
  v6 = (void *)*((_QWORD *)a1 + 7);
  if ( v6 )
  {
    WFDCloseHandleLib(v6);
    *((_QWORD *)a1 + 7) = 0;
  }
  v7 = (void *)*((_QWORD *)a1 + 121);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)a1 + 121) = 0;
  }
  v8 = (void *)*((_QWORD *)a1 + 122);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)a1 + 122) = 0;
  }
  if ( *((_DWORD *)a1 + 12) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
    *((_DWORD *)a1 + 12) = 0;
  }
  if ( *((_DWORD *)a1 + 18) )
    RemoveContextFromGlobalList(a1);
  FreeWLMem(a1);
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180038c50  mov     [rsp+arg_0], rbx
0x180038c55  mov     [rsp+arg_8], rdi
0x180038c5a  push    r14
0x180038c5c  sub     rsp, 20h
0x180038c60  mov     rbx, rcx
0x180038c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c6a  lea     r14, WPP_GLOBAL_Control
0x180038c71  cmp     rcx, r14
0x180038c74  jz      short loc_180038C97
0x180038c76  cmp     byte ptr [rcx+69h], 4
0x180038c7a  jb      short loc_180038C97
0x180038c7c  test    byte ptr [rcx+6Ch], 2
0x180038c80  jz      short loc_180038C97
0x180038c82  mov     rcx, [rcx+60h]
0x180038c86  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038c8d  mov     edx, 18h
0x180038c92  call    WPP_SF_
0x180038c97  mov     rdx, rbx; struct _WFD_OOB_SESSION_CONTEXT *
0x180038c9a  xor     ecx, ecx; int
0x180038c9c  call    ?WFDOobHelperRegisterForNotification@@YAKHPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOobHelperRegisterForNotification(int,_WFD_OOB_SESSION_CONTEXT *)
0x180038ca1  mov     edi, eax
0x180038ca3  test    eax, eax
0x180038ca5  jz      short loc_180038CD7
0x180038ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180038cae  cmp     rcx, r14
0x180038cb1  jz      short loc_180038CD7
0x180038cb3  cmp     byte ptr [rcx+69h], 1
0x180038cb7  jb      short loc_180038CD7
0x180038cb9  test    byte ptr [rcx+6Ch], 2
0x180038cbd  jz      short loc_180038CD7
0x180038cbf  mov     rcx, [rcx+60h]
0x180038cc3  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038cca  mov     edx, 19h
0x180038ccf  mov     r9d, eax
0x180038cd2  call    WPP_SF_d
0x180038cd7  cmp     dword ptr [rbx+44h], 0
0x180038cdb  jz      short loc_180038D1D
0x180038cdd  mov     rdx, rbx; struct _WFD_OOB_SESSION_CONTEXT *
0x180038ce0  xor     ecx, ecx; int
0x180038ce2  call    ?WFDOobHelperSetPCDiscoverable@@YAKHPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOobHelperSetPCDiscoverable(int,_WFD_OOB_SESSION_CONTEXT *)
0x180038ce7  mov     edi, eax
0x180038ce9  test    eax, eax
0x180038ceb  jz      short loc_180038D1D
0x180038ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180038cf4  cmp     rcx, r14
0x180038cf7  jz      short loc_180038D1D
0x180038cf9  cmp     byte ptr [rcx+69h], 1
0x180038cfd  jb      short loc_180038D1D
0x180038cff  test    byte ptr [rcx+6Ch], 2
0x180038d03  jz      short loc_180038D1D
0x180038d05  mov     rcx, [rcx+60h]
0x180038d09  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038d10  mov     edx, 1Ah
0x180038d15  mov     r9d, eax
0x180038d18  call    WPP_SF_d
0x180038d1d  mov     rcx, [rbx+398h]; void *
0x180038d24  test    rcx, rcx
0x180038d27  jz      short loc_180038D39
0x180038d29  call    ?WFDCloseSessionLib@@YAKPEAX@Z; WFDCloseSessionLib(void *)
0x180038d2e  mov     qword ptr [rbx+398h], 0
0x180038d39  mov     rcx, [rbx+38h]; void *
0x180038d3d  test    rcx, rcx
0x180038d40  jz      short loc_180038D4F
0x180038d42  call    ?WFDCloseHandleLib@@YAKPEAX@Z; WFDCloseHandleLib(void *)
0x180038d47  mov     qword ptr [rbx+38h], 0
0x180038d4f  mov     rcx, [rbx+3C8h]; hObject
0x180038d56  test    rcx, rcx
0x180038d59  jz      short loc_180038D6C
0x180038d5b  call    cs:__imp_CloseHandle
0x180038d61  mov     qword ptr [rbx+3C8h], 0
0x180038d6c  mov     rcx, [rbx+3D0h]; hObject
0x180038d73  test    rcx, rcx
0x180038d76  jz      short loc_180038D89
0x180038d78  call    cs:__imp_CloseHandle
0x180038d7e  mov     qword ptr [rbx+3D0h], 0
0x180038d89  cmp     dword ptr [rbx+30h], 0
0x180038d8d  jz      short loc_180038DA0
0x180038d8f  lea     rcx, [rbx+8]; lpCriticalSection
0x180038d93  call    cs:__imp_DeleteCriticalSection
0x180038d99  mov     dword ptr [rbx+30h], 0
0x180038da0  cmp     dword ptr [rbx+48h], 0
0x180038da4  jz      short loc_180038DAE
0x180038da6  mov     rcx, rbx; struct _WFD_OOB_SESSION_CONTEXT *
0x180038da9  call    ?RemoveContextFromGlobalList@@YAKPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; RemoveContextFromGlobalList(_WFD_OOB_SESSION_CONTEXT *)
0x180038dae  mov     rcx, rbx
0x180038db1  call    FreeWLMem
0x180038db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180038dbd  cmp     rcx, r14
0x180038dc0  jz      short loc_180038DE6
0x180038dc2  cmp     byte ptr [rcx+69h], 4
0x180038dc6  jb      short loc_180038DE6
0x180038dc8  test    byte ptr [rcx+6Ch], 2
0x180038dcc  jz      short loc_180038DE6
0x180038dce  mov     rcx, [rcx+60h]
0x180038dd2  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038dd9  mov     edx, 1Bh
0x180038dde  mov     r9d, edi
0x180038de1  call    WPP_SF_d
0x180038de6  mov     rbx, [rsp+28h+arg_0]
0x180038deb  mov     eax, edi
0x180038ded  mov     rdi, [rsp+28h+arg_8]
0x180038df2  add     rsp, 20h
0x180038df6  pop     r14
0x180038df8  retn
```
