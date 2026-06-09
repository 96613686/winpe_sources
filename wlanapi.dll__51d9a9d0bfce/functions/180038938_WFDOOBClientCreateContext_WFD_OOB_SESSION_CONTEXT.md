# WFDOOBClientCreateContext(_WFD_OOB_SESSION_CONTEXT * *)

- ea: `0x180038938`
- end: `0x180038c3f`
- name: `?WFDOOBClientCreateContext@@YAKPEAPEAU_WFD_OOB_SESSION_CONTEXT@@@Z`
- size: `775`
- prototype: `unsigned int __fastcall(struct _WFD_OOB_SESSION_CONTEXT **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180027ac0`
- `0x18002cd00`

## callees

- `0x1800038fc`
- `0x180005330`
- `0x1800063a0`
- `0x180006934`
- `0x18001a5bc`
- `0x180038938`
- `0x180038c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038a91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038ae3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038a91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038ae3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180038b2f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180038b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038af5`
- `MobileNetworking!HtNewHandle` at `0x180038b66`
- `MobileNetworking!HtNewHandle` at `0x180038b66`

## pseudocode

```c
__int64 __fastcall WFDOOBClientCreateContext(struct _WFD_OOB_SESSION_CONTEXT **a1)
{
  union DOT11_OUI_HEADER *v2; // rcx
  char *v3; // rdi
  unsigned int v4; // ebx
  char *Memory; // rax
  DWORD LastError; // eax
  __int64 v7; // rdx
  HANDLE EventW; // rax
  HANDLE v9; // rax
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF
  char *v13; // [rsp+60h] [rbp+18h]

  v12 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    *a1 = 0;
    Memory = (char *)WlanAllocateMemory(0x3F0u);
    v3 = Memory;
    v13 = Memory;
    if ( Memory )
    {
      memset_0(Memory, 0, 0x3F0u);
      LastError = WFDOpenHandleLib(1u, &v11, (void **)v3 + 7);
      v4 = LastError;
      if ( LastError )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
        {
          goto LABEL_38;
        }
        v7 = 18;
      }
      else
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)v3 + 121) = EventW;
        if ( EventW )
        {
          v9 = CreateEventW(0, 0, 0, 0);
          *((_QWORD *)v3 + 122) = v9;
          if ( v9 )
          {
            InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
            *((_DWORD *)v3 + 12) = 1;
            LastError = HtNewHandle(g_hHandleTable, v3, 269488144, WFDOOBClientDestroyContext, 1, &v12);
            v4 = LastError;
            if ( !LastError )
            {
              *(_QWORD *)v3 = v12;
              *a1 = (struct _WFD_OOB_SESSION_CONTEXT *)v3;
              v3 = 0;
              goto LABEL_10;
            }
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              || !*((_BYTE *)WPP_GLOBAL_Control + 105)
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
            {
              goto LABEL_38;
            }
            v7 = 22;
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
              || !*((_BYTE *)WPP_GLOBAL_Control + 105)
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
            {
              goto LABEL_38;
            }
            v7 = 20;
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 105)
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
          {
            goto LABEL_38;
          }
          v7 = 19;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_38;
      }
      v7 = 17;
    }
    WPP_SF_d(*((_QWORD *)v2 + 12), v7, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, LastError);
    goto LABEL_10;
  }
  v3 = 0;
  v4 = 87;
  if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) && (*((_BYTE *)v2 + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)v2 + 12), 16, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids);
LABEL_10:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_38:
  if ( v3 )
  {
    WFDOOBClientDestroyContext((struct _WFD_OOB_SESSION_CONTEXT *)v3);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v2 + 105) >= 4u
    && (*((_BYTE *)v2 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v2 + 12), 23, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180038938  mov     [rsp+arg_18], rbx
0x18003893d  push    rsi
0x18003893e  push    rdi
0x18003893f  push    r14
0x180038941  sub     rsp, 30h
0x180038945  mov     r14, rcx
0x180038948  mov     [rsp+48h+arg_8], 0
0x180038951  lea     rsi, WPP_GLOBAL_Control
0x180038958  mov     rcx, cs:WPP_GLOBAL_Control
0x18003895f  cmp     rcx, rsi
0x180038962  jz      short loc_18003898C
0x180038964  cmp     byte ptr [rcx+69h], 4
0x180038968  jb      short loc_18003898C
0x18003896a  test    byte ptr [rcx+6Ch], 2
0x18003896e  jz      short loc_18003898C
0x180038970  mov     edx, 0Fh
0x180038975  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x18003897c  mov     rcx, [rcx+60h]
0x180038980  call    WPP_SF_
0x180038985  mov     rcx, cs:WPP_GLOBAL_Control
0x18003898c  test    r14, r14
0x18003898f  jnz     short loc_1800389D2
0x180038991  xor     edi, edi
0x180038993  lea     ebx, [rdi+57h]
0x180038996  cmp     rcx, rsi
0x180038999  jz      loc_180038BF2
0x18003899f  cmp     byte ptr [rcx+69h], 1
0x1800389a3  jb      loc_180038BF2
0x1800389a9  test    byte ptr [rcx+6Ch], 2
0x1800389ad  jz      loc_180038BF2
0x1800389b3  lea     edx, [rdi+10h]
0x1800389b6  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x1800389bd  mov     rcx, [rcx+60h]
0x1800389c1  call    WPP_SF_
0x1800389c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800389cd  jmp     loc_180038BF2
0x1800389d2  mov     qword ptr [r14], 0
0x1800389d9  mov     ebx, 3F0h
0x1800389de  mov     ecx, ebx; dwMemorySize
0x1800389e0  call    WlanAllocateMemory
0x1800389e5  mov     rdi, rax
0x1800389e8  mov     [rsp+48h+arg_10], rax
0x1800389ed  test    rax, rax
0x1800389f0  jnz     short loc_180038A36
0x1800389f2  call    cs:__imp_GetLastError
0x1800389f8  mov     ebx, eax
0x1800389fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a01  cmp     rcx, rsi
0x180038a04  jz      loc_180038BF2
0x180038a0a  cmp     byte ptr [rcx+69h], 1
0x180038a0e  jb      loc_180038BF2
0x180038a14  test    byte ptr [rcx+6Ch], 2
0x180038a18  jz      loc_180038BF2
0x180038a1e  lea     edx, [rdi+11h]
0x180038a21  mov     r9d, eax
0x180038a24  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038a2b  mov     rcx, [rcx+60h]
0x180038a2f  call    WPP_SF_d
0x180038a34  jmp     short loc_1800389C6
0x180038a36  mov     r8, rbx; Size
0x180038a39  xor     edx, edx; Val
0x180038a3b  mov     rcx, rdi; void *
0x180038a3e  call    memset_0
0x180038a43  lea     r8, [rdi+38h]; void **
0x180038a47  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x180038a4c  mov     ecx, 1; unsigned int
0x180038a51  call    ?WFDOpenHandleLib@@YAKKPEAKPEAPEAX@Z; WFDOpenHandleLib(ulong,ulong *,void * *)
0x180038a56  mov     ebx, eax
0x180038a58  test    eax, eax
0x180038a5a  jz      short loc_180038A87
0x180038a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a63  cmp     rcx, rsi
0x180038a66  jz      loc_180038BF2
0x180038a6c  cmp     byte ptr [rcx+69h], 1
0x180038a70  jb      loc_180038BF2
0x180038a76  test    byte ptr [rcx+6Ch], 2
0x180038a7a  jz      loc_180038BF2
0x180038a80  mov     edx, 12h
0x180038a85  jmp     short loc_180038A21
0x180038a87  xor     r9d, r9d; lpName
0x180038a8a  xor     r8d, r8d; bInitialState
0x180038a8d  xor     edx, edx; bManualReset
0x180038a8f  xor     ecx, ecx; lpEventAttributes
0x180038a91  call    cs:__imp_CreateEventW
0x180038a97  mov     [rdi+3C8h], rax
0x180038a9e  test    rax, rax
0x180038aa1  jnz     short loc_180038AD9
0x180038aa3  call    cs:__imp_GetLastError
0x180038aa9  mov     ebx, eax
0x180038aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ab2  cmp     rcx, rsi
0x180038ab5  jz      loc_180038BF2
0x180038abb  cmp     byte ptr [rcx+69h], 1
0x180038abf  jb      loc_180038BF2
0x180038ac5  test    byte ptr [rcx+6Ch], 2
0x180038ac9  jz      loc_180038BF2
0x180038acf  mov     edx, 13h
0x180038ad4  jmp     loc_180038A21
0x180038ad9  xor     r9d, r9d; lpName
0x180038adc  xor     r8d, r8d; bInitialState
0x180038adf  xor     edx, edx; bManualReset
0x180038ae1  xor     ecx, ecx; lpEventAttributes
0x180038ae3  call    cs:__imp_CreateEventW
0x180038ae9  mov     [rdi+3D0h], rax
0x180038af0  test    rax, rax
0x180038af3  jnz     short loc_180038B2B
0x180038af5  call    cs:__imp_GetLastError
0x180038afb  mov     ebx, eax
0x180038afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b04  cmp     rcx, rsi
0x180038b07  jz      loc_180038BF2
0x180038b0d  cmp     byte ptr [rcx+69h], 1
0x180038b11  jb      loc_180038BF2
0x180038b17  test    byte ptr [rcx+6Ch], 2
0x180038b1b  jz      loc_180038BF2
0x180038b21  mov     edx, 14h
0x180038b26  jmp     loc_180038A21
0x180038b2b  lea     rcx, [rdi+8]; lpCriticalSection
0x180038b2f  call    cs:__imp_InitializeCriticalSection
0x180038b35  nop
0x180038b36  mov     dword ptr [rdi+30h], 1
0x180038b3d  lea     rax, [rsp+48h+arg_8]
0x180038b42  mov     [rsp+48h+var_20], rax
0x180038b47  mov     [rsp+48h+var_28], 1
0x180038b4f  lea     r9, ?WFDOOBClientDestroyContext@@YAKPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOOBClientDestroyContext(_WFD_OOB_SESSION_CONTEXT *)
0x180038b56  mov     r8d, 10101010h
0x180038b5c  mov     rdx, rdi
0x180038b5f  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180038b66  call    cs:__imp_HtNewHandle
0x180038b6c  mov     ebx, eax
0x180038b6e  test    eax, eax
0x180038b70  jz      short loc_180038B94
0x180038b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b79  cmp     rcx, rsi
0x180038b7c  jz      short loc_180038BF2
0x180038b7e  cmp     byte ptr [rcx+69h], 1
0x180038b82  jb      short loc_180038BF2
0x180038b84  test    byte ptr [rcx+6Ch], 2
0x180038b88  jz      short loc_180038BF2
0x180038b8a  mov     edx, 16h
0x180038b8f  jmp     loc_180038A21
0x180038b94  mov     rax, [rsp+48h+arg_8]
0x180038b99  mov     [rdi], rax
0x180038b9c  mov     [r14], rdi
0x180038b9f  xor     edi, edi
0x180038ba1  jmp     loc_1800389C6
0x180038ba6  mov     ebx, eax
0x180038ba8  lea     rax, WPP_GLOBAL_Control
0x180038baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180038bb6  cmp     rcx, rax
0x180038bb9  jz      short loc_180038BE6
0x180038bbb  cmp     byte ptr [rcx+69h], 1
0x180038bbf  jb      short loc_180038BE6
0x180038bc1  test    byte ptr [rcx+6Ch], 2
0x180038bc5  jz      short loc_180038BE6
0x180038bc7  mov     edx, 15h
0x180038bcc  mov     r9d, ebx
0x180038bcf  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038bd6  mov     rcx, [rcx+60h]
0x180038bda  call    WPP_SF_d
0x180038bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180038be6  lea     rsi, WPP_GLOBAL_Control
0x180038bed  mov     rdi, [rsp+48h+arg_10]
0x180038bf2  test    rdi, rdi
0x180038bf5  jz      short loc_180038C06
0x180038bf7  mov     rcx, rdi; struct _WFD_OOB_SESSION_CONTEXT *
0x180038bfa  call    ?WFDOOBClientDestroyContext@@YAKPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOOBClientDestroyContext(_WFD_OOB_SESSION_CONTEXT *)
0x180038bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c06  cmp     rcx, rsi
0x180038c09  jz      short loc_180038C2F
0x180038c0b  cmp     byte ptr [rcx+69h], 4
0x180038c0f  jb      short loc_180038C2F
0x180038c11  test    byte ptr [rcx+6Ch], 2
0x180038c15  jz      short loc_180038C2F
0x180038c17  mov     edx, 17h
0x180038c1c  mov     r9d, ebx
0x180038c1f  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038c26  mov     rcx, [rcx+60h]
0x180038c2a  call    WPP_SF_d
0x180038c2f  mov     eax, ebx
0x180038c31  mov     rbx, [rsp+48h+arg_18]
0x180038c36  add     rsp, 30h
0x180038c3a  pop     r14
0x180038c3c  pop     rdi
0x180038c3d  pop     rsi
0x180038c3e  retn
```
