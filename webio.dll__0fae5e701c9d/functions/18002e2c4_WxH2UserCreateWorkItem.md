# WxH2UserCreateWorkItem

- ea: `0x18002e2c4`
- end: `0x18002e44b`
- name: `WxH2UserCreateWorkItem`
- size: `391`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002d2fc`
- `0x18002d3c0`
- `0x18002ea44`
- `0x18002ec54`
- `0x18002f864`

## callees

- `0x180013820`
- `0x180014f30`
- `0x18002e2c4`
- `0x18002e460`
- `0x1800722f0`
- `0x180072c70`
- `0x180098010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e38f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002e38f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e30e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e30e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e34a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e34a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002e3ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002e3ff`

## pseudocode

```c
__int64 __fastcall WxH2UserCreateWorkItem(_QWORD *a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  PTP_WORK ThreadpoolWork; // rax
  HANDLE *v10; // rsi
  unsigned int CurrentThreadToken; // eax
  unsigned int v12; // ebp
  unsigned int LastError; // edi
  struct _TP_WORK *v15; // rcx
  __int128 v16; // [rsp+20h] [rbp-58h] BYREF

  v3 = g_fWxHeapExtensionInitialized == 0;
  *a1 = 0;
  if ( v3 )
    v7 = HeapAlloc(g_hWxProcessHeap, 0, 0x40u);
  else
    v7 = (_DWORD *)((__int64 (__fastcall *)(__int64))qword_1800AE528)(64);
  v8 = v7;
  if ( !v7 )
    return 8;
  memset_0(v7, 0, 0x40u);
  *v8 = 1331122260;
  ThreadpoolWork = CreateThreadpoolWork(WapTpWorkItemCallback, v8, &WaTpEnvironment);
  *((_QWORD *)v8 + 1) = ThreadpoolWork;
  v10 = (HANDLE *)(v8 + 8);
  if ( ThreadpoolWork )
  {
    *((_QWORD *)v8 + 2) = a2;
    *((_QWORD *)v8 + 3) = a3;
    *v10 = 0;
    CurrentThreadToken = WaGetCurrentThreadToken((__int64 *)v8 + 4);
    v12 = CurrentThreadToken;
    if ( !CurrentThreadToken )
    {
      v16 = 0;
      if ( EventActivityIdControl(1u, (LPGUID)(v8 + 10)) )
        *(_OWORD *)(v8 + 10) = 0;
      *((_BYTE *)v8 + 56) = 1;
      LastError = 0;
      goto LABEL_9;
    }
    *v10 = 0;
    LastError = CurrentThreadToken;
  }
  else
  {
    LastError = WaGetLastError();
    v12 = LastError;
    if ( !LastError )
      goto LABEL_12;
  }
  v15 = (struct _TP_WORK *)*((_QWORD *)v8 + 1);
  if ( v15 )
    CloseThreadpoolWork(v15);
  if ( *v10 )
  {
    CloseHandle(*v10);
    goto LABEL_13;
  }
LABEL_12:
  LastError = v12;
  if ( v12 )
  {
LABEL_13:
    *(_QWORD *)&v16 = v8;
    WxFreeHeapEx(&v16);
    return LastError;
  }
LABEL_9:
  *a1 = v8;
  return LastError;
}

```

## disassembly

```asm
0x18002e2c4  push    rbx
0x18002e2c6  push    rbp
0x18002e2c7  push    rsi
0x18002e2c8  push    rdi
0x18002e2c9  push    r14
0x18002e2cb  push    r15
0x18002e2cd  sub     rsp, 48h
0x18002e2d1  mov     rax, cs:__security_cookie
0x18002e2d8  xor     rax, rsp
0x18002e2db  mov     [rsp+78h+var_48], rax
0x18002e2e0  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18002e2e7  mov     rbp, r8
0x18002e2ea  mov     r15, rdx
0x18002e2ed  mov     qword ptr [rcx], 0
0x18002e2f4  mov     r14, rcx
0x18002e2f7  mov     edi, 40h ; '@'
0x18002e2fc  jnz     loc_18002E421
0x18002e302  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18002e309  mov     r8d, edi; dwBytes
0x18002e30c  xor     edx, edx; dwFlags
0x18002e30e  call    cs:__imp_HeapAlloc
0x18002e315  nop     dword ptr [rax+rax+00h]
0x18002e31a  mov     rbx, rax
0x18002e31d  test    rax, rax
0x18002e320  jz      loc_18002E435
0x18002e326  mov     r8, rdi; Size
0x18002e329  xor     edx, edx; Val
0x18002e32b  mov     rcx, rax; void *
0x18002e32e  call    memset_0
0x18002e333  lea     r8, WaTpEnvironment; pcbe
0x18002e33a  mov     dword ptr [rbx], 4F575054h
0x18002e340  mov     rdx, rbx; pv
0x18002e343  lea     rcx, WapTpWorkItemCallback; pfnwk
0x18002e34a  call    cs:__imp_CreateThreadpoolWork
0x18002e351  nop     dword ptr [rax+rax+00h]
0x18002e356  mov     [rbx+8], rax
0x18002e35a  lea     rsi, [rbx+20h]
0x18002e35e  test    rax, rax
0x18002e361  jz      short loc_18002E3C9
0x18002e363  mov     rcx, rsi
0x18002e366  mov     [rbx+10h], r15
0x18002e36a  mov     [rbx+18h], rbp
0x18002e36e  mov     qword ptr [rsi], 0
0x18002e375  call    WaGetCurrentThreadToken
0x18002e37a  mov     ebp, eax
0x18002e37c  test    eax, eax
0x18002e37e  jnz     short loc_18002E3ED
0x18002e380  xorps   xmm0, xmm0
0x18002e383  lea     rdx, [rbx+28h]; ActivityId
0x18002e387  lea     ecx, [rax+1]; ControlCode
0x18002e38a  movups  [rsp+78h+var_58], xmm0
0x18002e38f  call    cs:__imp_EventActivityIdControl
0x18002e396  nop     dword ptr [rax+rax+00h]
0x18002e39b  test    eax, eax
0x18002e39d  jnz     loc_18002E43F
0x18002e3a3  mov     byte ptr [rbx+38h], 1
0x18002e3a7  xor     edi, edi
0x18002e3a9  mov     [r14], rbx
0x18002e3ac  mov     eax, edi
0x18002e3ae  mov     rcx, [rsp+78h+var_48]
0x18002e3b3  xor     rcx, rsp; StackCookie
0x18002e3b6  call    __security_check_cookie
0x18002e3bb  add     rsp, 48h
0x18002e3bf  pop     r15
0x18002e3c1  pop     r14
0x18002e3c3  pop     rdi
0x18002e3c4  pop     rsi
0x18002e3c5  pop     rbp
0x18002e3c6  pop     rbx
0x18002e3c7  retn
0x18002e3c9  call    WaGetLastError
0x18002e3ce  mov     edi, eax
0x18002e3d0  mov     ebp, eax
0x18002e3d2  test    eax, eax
0x18002e3d4  jnz     short loc_18002E3F6
0x18002e3d6  mov     edi, ebp
0x18002e3d8  test    ebp, ebp
0x18002e3da  jz      short loc_18002E3A9
0x18002e3dc  lea     rcx, [rsp+78h+var_58]
0x18002e3e1  mov     qword ptr [rsp+78h+var_58], rbx
0x18002e3e6  call    WxFreeHeapEx
0x18002e3eb  jmp     short loc_18002E3AC
0x18002e3ed  mov     qword ptr [rsi], 0
0x18002e3f4  mov     edi, eax
0x18002e3f6  mov     rcx, [rbx+8]; pwk
0x18002e3fa  test    rcx, rcx
0x18002e3fd  jz      short loc_18002E40B
0x18002e3ff  call    cs:__imp_CloseThreadpoolWork
0x18002e406  nop     dword ptr [rax+rax+00h]
0x18002e40b  mov     rcx, [rsi]; hObject
0x18002e40e  test    rcx, rcx
0x18002e411  jz      short loc_18002E3D6
0x18002e413  call    cs:__imp_CloseHandle
0x18002e41a  nop     dword ptr [rax+rax+00h]
0x18002e41f  jmp     short loc_18002E3DC
0x18002e421  mov     rax, cs:qword_1800AE528
0x18002e428  mov     rcx, rdi
0x18002e42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e430  jmp     loc_18002E31A
0x18002e435  mov     edi, 8
0x18002e43a  jmp     loc_18002E3AC
0x18002e43f  xorps   xmm0, xmm0
0x18002e442  movups  xmmword ptr [rbx+28h], xmm0
0x18002e446  jmp     loc_18002E3A3
```
