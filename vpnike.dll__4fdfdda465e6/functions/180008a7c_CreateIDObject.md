# CreateIDObject

- ea: `0x180008a7c`
- end: `0x180008df1`
- name: `CreateIDObject`
- size: `885`
- prototype: `__int64 __fastcall(unsigned __int8, unsigned int, const char *, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180042ad8`
- `0x1800435d0`
- `0x1800516d0`
- `0x180051d30`

## callees

- `0x180007590`
- `0x1800077bc`
- `0x180008a7c`
- `0x18000a3a0`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x180077552`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ceb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ceb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cdd`

## string_xrefs

- `0x180008b5a`: `CreateIDObject`
- `0x180008bb1`: `CreateIDiObject: Failed to allocate memory for IKE_ID_PAYLOAD`
- `0x180008c0b`: `CreateIDiObject: Creating IKE_ID_PAYLOAD with ID type as (%d) , idLength as (%d) and ID as (%s)`
- `0x180008cbb`: `CreateIDiObject: Failed to allocate memory for IKE_ID_PAYLOAD::data`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateIDObject(unsigned __int8 a1, unsigned int a2, const char *a3, __int64 a4)
{
  SIZE_T v5; // rsi
  unsigned int v7; // r15d
  PVOID *v8; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const char *v13; // rax
  HANDLE v14; // rax
  void *v15; // rcx
  void *v16; // rbx
  HANDLE v17; // rax
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v5 = a2;
  v7 = a1;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, a1, a2);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v19 = 0;
  v22 = 0;
  v20 = 0;
  v23 = -1;
  v21 = 0;
  v24 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"CreateIDObject",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 && (!(_DWORD)v5 || a3) )
  {
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    *(_QWORD *)a4 = v10;
    if ( !v10 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"CreateIDiObject: Failed to allocate memory for IKE_ID_PAYLOAD");
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        goto LABEL_34;
      }
      v12 = 24;
LABEL_33:
      WPP_SF_d(v11[2], v12, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, 8);
LABEL_34:
      EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
      return 8;
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v25) = 0;
      v13 = "nullptr";
      if ( a3 )
        v13 = a3;
      FormatRRASErrorString(
        &v25,
        L"CreateIDiObject: Creating IKE_ID_PAYLOAD with ID type as (%d) , idLength as (%d) and ID as (%s)",
        v7,
        (unsigned int)v5,
        v13);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v25);
    }
    *(_BYTE *)(*(_QWORD *)a4 + 4LL) = v7;
    **(_DWORD **)a4 = v5;
    *(_QWORD *)(*(_QWORD *)a4 + 8LL) = 0;
    if ( (_DWORD)v5 && a3 )
    {
      v14 = GetProcessHeap();
      *(_QWORD *)(*(_QWORD *)a4 + 8LL) = HeapAlloc(v14, 8u, v5);
      v15 = *(void **)(*(_QWORD *)a4 + 8LL);
      if ( !v15 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasVpnIkeTraceError,
            L"CreateIDiObject: Failed to allocate memory for IKE_ID_PAYLOAD::data");
        v16 = *(void **)a4;
        if ( *(_QWORD *)a4 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v16);
        }
        *(_QWORD *)a4 = 0;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
        {
          goto LABEL_34;
        }
        v12 = 25;
        goto LABEL_33;
      }
      memcpy_0(v15, a3, v5);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, 0);
    }
    EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
    return 0;
  }
  else
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      WPP_SF_d(v8[2], 23, &WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids, 87);
    EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
    return 87;
  }
}

```

## disassembly

```asm
0x180008a7c  push    rbp
0x180008a7e  push    rbx
0x180008a7f  push    rsi
0x180008a80  push    rdi
0x180008a81  push    r13
0x180008a83  push    r14
0x180008a85  push    r15
0x180008a87  lea     rbp, [rsp-780h]
0x180008a8f  sub     rsp, 880h
0x180008a96  mov     rax, cs:__security_cookie
0x180008a9d  xor     rax, rsp
0x180008aa0  mov     [rbp+7B0h+var_40], rax
0x180008aa7  mov     rdi, r9
0x180008aaa  mov     esi, edx
0x180008aac  mov     r14, r8
0x180008aaf  movzx   r15d, cl
0x180008ab3  mov     rbx, cs:WPP_GLOBAL_Control
0x180008aba  lea     rax, WPP_GLOBAL_Control
0x180008ac1  cmp     rbx, rax
0x180008ac4  jz      short loc_180008AF5
0x180008ac6  test    byte ptr [rbx+1Ch], 1
0x180008aca  jz      short loc_180008AF5
0x180008acc  cmp     byte ptr [rbx+19h], 6
0x180008ad0  jb      short loc_180008AF5
0x180008ad2  mov     rcx, [rbx+10h]
0x180008ad6  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x180008add  mov     r9d, r15d
0x180008ae0  mov     dword ptr [rsp+8B0h+var_890], esi
0x180008ae4  mov     edx, 16h
0x180008ae9  call    WPP_SF_dd
0x180008aee  mov     rbx, cs:WPP_GLOBAL_Control
0x180008af5  xor     eax, eax
0x180008af7  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180008afc  xor     edx, edx; Val
0x180008afe  mov     [rsp+8B0h+var_840], eax
0x180008b02  mov     r8d, 7FCh; Size
0x180008b08  call    memset_0
0x180008b0d  mov     r13d, 8
0x180008b13  mov     [rsp+8B0h+var_878], 0
0x180008b1c  test    cs:byte_1800AA941, r13b
0x180008b23  xorps   xmm0, xmm0
0x180008b26  xorps   xmm1, xmm1
0x180008b29  mov     [rsp+8B0h+var_850], 0
0x180008b32  movdqu  [rsp+8B0h+var_870], xmm0
0x180008b38  mov     [rsp+8B0h+var_848], 0FFFFFFFFh
0x180008b40  movdqu  [rsp+8B0h+var_860], xmm1
0x180008b46  mov     [rsp+8B0h+var_844], 0
0x180008b4e  jz      short loc_180008B72
0x180008b50  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180008b57  xor     r8d, r8d; unsigned int *
0x180008b5a  lea     rdx, aCreateidobject; "CreateIDObject"
0x180008b61  lea     rcx, [rsp+8B0h+var_878]; this
0x180008b66  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180008b6b  mov     rbx, cs:WPP_GLOBAL_Control
0x180008b72  test    rdi, rdi
0x180008b75  jz      loc_180008D91
0x180008b7b  test    esi, esi
0x180008b7d  jz      short loc_180008B88
0x180008b7f  test    r14, r14
0x180008b82  jz      loc_180008D91
0x180008b88  call    cs:__imp_GetProcessHeap
0x180008b8e  mov     r8d, 10h; dwBytes
0x180008b94  mov     edx, r13d; dwFlags
0x180008b97  mov     rcx, rax; hHeap
0x180008b9a  call    cs:__imp_HeapAlloc
0x180008ba0  mov     [rdi], rax
0x180008ba3  test    rax, rax
0x180008ba6  jnz     short loc_180008C00
0x180008ba8  test    cs:byte_1800AA941, 4
0x180008baf  jz      short loc_180008BCB
0x180008bb1  lea     r8, aCreateidiobjec; "CreateIDiObject: Failed to allocate mem"...
0x180008bb8  lea     rdx, RasVpnIkeTraceError
0x180008bbf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008bc6  call    McTemplateU0z_EventWriteTransfer
0x180008bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bd2  lea     rax, WPP_GLOBAL_Control
0x180008bd9  cmp     rcx, rax
0x180008bdc  jz      loc_180008D2F
0x180008be2  test    byte ptr [rcx+1Ch], 1
0x180008be6  jz      loc_180008D2F
0x180008bec  cmp     byte ptr [rcx+19h], 6
0x180008bf0  jb      loc_180008D2F
0x180008bf6  mov     edx, 18h
0x180008bfb  jmp     loc_180008D1C
0x180008c00  test    cs:byte_1800AA941, r13b
0x180008c07  jz      short loc_180008C5B
0x180008c09  xor     eax, eax
0x180008c0b  lea     rdx, aCreateidiobjec_0; "CreateIDiObject: Creating IKE_ID_PAYLOA"...
0x180008c12  mov     word ptr [rsp+8B0h+var_840], ax
0x180008c17  lea     rcx, [rsp+8B0h+var_840]
0x180008c1c  test    r14, r14
0x180008c1f  lea     rax, aNullptr; "nullptr"
0x180008c26  mov     r8d, r15d
0x180008c29  mov     r9d, esi
0x180008c2c  cmovnz  rax, r14
0x180008c30  mov     [rsp+8B0h+var_890], rax
0x180008c35  call    FormatRRASErrorString
0x180008c3a  test    cs:byte_1800AA941, r13b
0x180008c41  jz      short loc_180008C5B
0x180008c43  lea     r8, [rsp+8B0h+var_840]
0x180008c48  lea     rdx, RasVpnIkeTraceInfo
0x180008c4f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008c56  call    McTemplateU0z_EventWriteTransfer
0x180008c5b  mov     rax, [rdi]
0x180008c5e  mov     [rax+4], r15b
0x180008c62  mov     rax, [rdi]
0x180008c65  mov     [rax], esi
0x180008c67  mov     rax, [rdi]
0x180008c6a  mov     qword ptr [rax+8], 0
0x180008c72  test    esi, esi
0x180008c74  jz      loc_180008D4C
0x180008c7a  test    r14, r14
0x180008c7d  jz      loc_180008D4C
0x180008c83  call    cs:__imp_GetProcessHeap
0x180008c89  mov     r8, rsi; dwBytes
0x180008c8c  mov     edx, r13d; dwFlags
0x180008c8f  mov     rcx, rax; hHeap
0x180008c92  call    cs:__imp_HeapAlloc
0x180008c98  mov     rcx, rax
0x180008c9b  mov     rax, [rdi]
0x180008c9e  mov     [rax+8], rcx
0x180008ca2  mov     rax, [rdi]
0x180008ca5  mov     rcx, [rax+8]; void *
0x180008ca9  test    rcx, rcx
0x180008cac  jnz     loc_180008D41
0x180008cb2  test    cs:byte_1800AA941, 4
0x180008cb9  jz      short loc_180008CD5
0x180008cbb  lea     r8, aCreateidiobjec_1; "CreateIDiObject: Failed to allocate mem"...
0x180008cc2  lea     rdx, RasVpnIkeTraceError
0x180008cc9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008cd0  call    McTemplateU0z_EventWriteTransfer
0x180008cd5  mov     rbx, [rdi]
0x180008cd8  test    rbx, rbx
0x180008cdb  jz      short loc_180008CF1
0x180008cdd  call    cs:__imp_GetProcessHeap
0x180008ce3  mov     r8, rbx; lpMem
0x180008ce6  xor     edx, edx; dwFlags
0x180008ce8  mov     rcx, rax; hHeap
0x180008ceb  call    cs:__imp_HeapFree
0x180008cf1  mov     qword ptr [rdi], 0
0x180008cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cff  lea     rax, WPP_GLOBAL_Control
0x180008d06  cmp     rcx, rax
0x180008d09  jz      short loc_180008D2F
0x180008d0b  test    byte ptr [rcx+1Ch], 1
0x180008d0f  jz      short loc_180008D2F
0x180008d11  cmp     byte ptr [rcx+19h], 6
0x180008d15  jb      short loc_180008D2F
0x180008d17  mov     edx, 19h
0x180008d1c  mov     rcx, [rcx+10h]
0x180008d20  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x180008d27  mov     r9d, r13d
0x180008d2a  call    WPP_SF_d
0x180008d2f  lea     rcx, [rsp+8B0h+var_878]; this
0x180008d34  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180008d39  mov     eax, r13d
0x180008d3c  jmp     loc_180008DD0
0x180008d41  mov     r8, rsi; Size
0x180008d44  mov     rdx, r14; Src
0x180008d47  call    memcpy_0
0x180008d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d53  lea     rax, WPP_GLOBAL_Control
0x180008d5a  cmp     rcx, rax
0x180008d5d  jz      short loc_180008D83
0x180008d5f  test    byte ptr [rcx+1Ch], 1
0x180008d63  jz      short loc_180008D83
0x180008d65  cmp     byte ptr [rcx+19h], 6
0x180008d69  jb      short loc_180008D83
0x180008d6b  mov     rcx, [rcx+10h]
0x180008d6f  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x180008d76  mov     edx, 1Ah
0x180008d7b  xor     r9d, r9d
0x180008d7e  call    WPP_SF_d
0x180008d83  lea     rcx, [rsp+8B0h+var_878]; this
0x180008d88  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180008d8d  xor     eax, eax
0x180008d8f  jmp     short loc_180008DD0
0x180008d91  lea     rax, WPP_GLOBAL_Control
0x180008d98  mov     edi, 57h ; 'W'
0x180008d9d  cmp     rbx, rax
0x180008da0  jz      short loc_180008DC4
0x180008da2  test    byte ptr [rbx+1Ch], 1
0x180008da6  jz      short loc_180008DC4
0x180008da8  cmp     byte ptr [rbx+19h], 6
0x180008dac  jb      short loc_180008DC4
0x180008dae  mov     rcx, [rbx+10h]
0x180008db2  lea     edx, [rdi-40h]
0x180008db5  mov     r9d, edi
0x180008db8  lea     r8, WPP_91d98fef5f143f5b96f1a3fcbe8f5039_Traceguids
0x180008dbf  call    WPP_SF_d
0x180008dc4  lea     rcx, [rsp+8B0h+var_878]; this
0x180008dc9  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180008dce  mov     eax, edi
0x180008dd0  mov     rcx, [rbp+7B0h+var_40]
0x180008dd7  xor     rcx, rsp; StackCookie
0x180008dda  call    __security_check_cookie
0x180008ddf  add     rsp, 880h
0x180008de6  pop     r15
0x180008de8  pop     r14
0x180008dea  pop     r13
0x180008dec  pop     rdi
0x180008ded  pop     rsi
0x180008dee  pop     rbx
0x180008def  pop     rbp
0x180008df0  retn
```
