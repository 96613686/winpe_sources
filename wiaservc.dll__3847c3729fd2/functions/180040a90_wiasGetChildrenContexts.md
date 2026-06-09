# wiasGetChildrenContexts

- ea: `0x180040a90`
- end: `0x180040edc`
- name: `wiasGetChildrenContexts`
- size: `1100`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x1800189cc`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180040a90`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180040e6b`
- `ole32!CoTaskMemFree` at `0x180040e6b`
- `ole32!CoTaskMemAlloc` at `0x180040d25`
- `ole32!CoTaskMemAlloc` at `0x180040d25`

## pseudocode

```c
__int64 __fastcall wiasGetChildrenContexts(struct IWiaItem *a1, _DWORD *a2, _QWORD *a3)
{
  int v6; // edi
  char *v7; // rbx
  void *v8; // rdx
  void **lpMem; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  void *v13; // r15
  char *v14; // rbx
  void *v15; // rdx
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  __int64 *v19; // r8
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  __int64 *v25; // rcx
  __int64 v26; // rax
  char *v27; // rbx
  void *v28; // rdx
  unsigned int v29; // eax
  char *v30; // rbx
  void *v31; // rdx
  void **v32; // rax
  void *v33; // rdx
  __int64 v34; // rcx
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rbx
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  int v46; // [rsp+30h] [rbp-30h] BYREF
  __int64 *v47; // [rsp+38h] [rbp-28h] BYREF
  __int64 *v48; // [rsp+40h] [rbp-20h] BYREF
  __int64 v49; // [rsp+48h] [rbp-18h] BYREF
  __int64 v50; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v51; // [rsp+90h] [rbp+30h] BYREF
  int v52; // [rsp+A8h] [rbp+48h] BYREF

  v51 = 0;
  v50 = 0;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  v52 = 0;
  v6 = ValidateWiaItem(a1);
  if ( v6 < 0 )
  {
    v7 = (char *)WiaTrace_TraceLog("wiasGetChildrenContexts, invalid pParentContext");
    WriteDbgTraceErrorWI("wiasGetChildrenContexts", v7);
    WiaTrcLib::Free((WiaTrcLib *)v7, v8);
    lpMem = (void **)WiaTrace_Trace("wiasGetChildrenContexts, invalid pParentContext");
    WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"wiasGetChildrenContexts", 1, lpMem);
    return (unsigned int)v6;
  }
  if ( a1 && a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v13 = 0;
    v6 = ((__int64 (__fastcall *)(struct IWiaItem *, int *))a1[5].lpVtbl->EnumChildItems)(&a1[5], &v52);
    if ( v6 < 0 )
    {
      v14 = (char *)WiaTrace_TraceLog("wiasGetChildrenContexts, GetItemType failed (0x%X)");
      WriteDbgTraceErrorWI("wiasGetChildrenContexts", v14);
      WiaTrcLib::Free((WiaTrcLib *)v14, v15);
      v16 = (void **)WiaTrace_Trace("wiasGetChildrenContexts, GetItemType failed (0x%X)", (unsigned int)v6);
LABEL_9:
      WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"wiasGetChildrenContexts", 1, v16);
LABEL_38:
      if ( v52 == 2 )
      {
        if ( v47 )
        {
          (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
          v47 = 0;
        }
      }
      else if ( v48 )
      {
        (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
        v48 = 0;
      }
      if ( v6 < 0 )
      {
        if ( v13 )
          CoTaskMemFree(v13);
      }
      return (unsigned int)v6;
    }
    if ( v52 == 2 )
    {
      v6 = ((__int64 (__fastcall *)(struct IWiaItem *, _QWORD, __int64 **))a1[7].lpVtbl->EnumChildItems)(
             &a1[7],
             0,
             &v47);
      if ( v6 < 0 )
        goto LABEL_15;
      v19 = v47;
      if ( !v47 )
        v6 = -2147467261;
      if ( v6 < 0 )
        goto LABEL_15;
      v25 = v48;
LABEL_17:
      if ( v52 == 2 )
      {
        v26 = *v19;
        v25 = v19;
      }
      else
      {
        v26 = *v25;
      }
      v6 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v26 + 56))(v25, &v51);
      if ( v6 >= 0 )
      {
        v29 = v51;
        if ( !v51 )
        {
          v30 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasGetChildrenContexts, no children (S_FALSE)");
          WriteDbgTraceWarningWI("wiasGetChildrenContexts", v30);
          WiaTrcLib::Free((WiaTrcLib *)v30, v31);
          v32 = (void **)WiaTrace_TraceWithSubComp(0, "wiasGetChildrenContexts, no children (S_FALSE)");
          WiaTrace_ProcessTrace_Ex(v34, v33, (void *)"wiasGetChildrenContexts", 2, v32);
          v29 = v51;
        }
        v13 = CoTaskMemAlloc(8LL * v29);
        if ( v13 )
        {
          v40 = 0;
          v46 = 0;
          if ( v52 == 2 )
          {
            while ( !(*(unsigned int (__fastcall **)(__int64 *, __int64, __int64 *, int *))(*v47 + 24))(
                       v47,
                       1,
                       &v49,
                       &v46)
                 && (unsigned int)v40 < v51 )
            {
              *((_QWORD *)v13 + v40) = v49;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              v40 = (unsigned int)(v40 + 1);
            }
          }
          else
          {
            while ( !(*(unsigned int (__fastcall **)(__int64 *, __int64, __int64 *, int *))(*v48 + 24))(
                       v48,
                       1,
                       &v50,
                       &v46)
                 && (unsigned int)v40 < v51 )
            {
              *((_QWORD *)v13 + v40) = v50;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
              v40 = (unsigned int)(v40 + 1);
            }
          }
          *a2 = v40;
          v6 = 0;
          *a3 = v13;
        }
        else
        {
          v35 = (char *)WiaTrace_TraceLog("wiasGetChildrenContexts, out of memory");
          WriteDbgTraceErrorWI("wiasGetChildrenContexts", v35);
          WiaTrcLib::Free((WiaTrcLib *)v35, v36);
          v37 = (void **)WiaTrace_Trace("wiasGetChildrenContexts, out of memory");
          WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"wiasGetChildrenContexts", 1, v37);
          v6 = -2147024882;
        }
        goto LABEL_38;
      }
      v27 = (char *)WiaTrace_TraceLog("wiasGetChildrenContexts, IEnumWiaItemX::GetCount failed (0x%X)");
      WriteDbgTraceErrorWI("wiasGetChildrenContexts", v27);
      WiaTrcLib::Free((WiaTrcLib *)v27, v28);
      v16 = (void **)WiaTrace_Trace("wiasGetChildrenContexts, IEnumWiaItemX::GetCount failed (0x%X)", (unsigned int)v6);
      goto LABEL_9;
    }
    v6 = ((__int64 (__fastcall *)(struct IWiaItem *, __int64 **))a1->lpVtbl->EnumChildItems)(a1, &v48);
    if ( v6 >= 0 )
    {
      v25 = v48;
      if ( v48 )
      {
        v19 = v47;
        goto LABEL_17;
      }
      v6 = -2147467261;
    }
LABEL_15:
    v20 = (char *)WiaTrace_TraceLog("wiasGetChildrenContexts, IWiaItemX::EnumChildItems failed (0x%X)");
    WriteDbgTraceErrorWI("wiasGetChildrenContexts", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void **)WiaTrace_Trace("wiasGetChildrenContexts, IWiaItemX::EnumChildItems failed (0x%X)", v6);
    WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"wiasGetChildrenContexts", 1, v22);
    goto LABEL_38;
  }
  v41 = (char *)WiaTrace_TraceLog("wiasGetChildrenContexts, Invalid pointer argument");
  WriteDbgTraceErrorWI("wiasGetChildrenContexts", v41);
  WiaTrcLib::Free((WiaTrcLib *)v41, v42);
  v43 = (void **)WiaTrace_Trace("wiasGetChildrenContexts, Invalid pointer argument");
  WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"wiasGetChildrenContexts", 1, v43);
  return 2147500035LL;
}

```

## disassembly

```asm
0x180040a90  mov     [rsp-28h+arg_8], rbx
0x180040a95  mov     [rsp-28h+arg_10], rsi
0x180040a9a  push    rbp
0x180040a9b  push    rdi
0x180040a9c  push    r12
0x180040a9e  push    r13
0x180040aa0  push    r15
0x180040aa2  mov     rbp, rsp
0x180040aa5  sub     rsp, 60h
0x180040aa9  xor     esi, esi
0x180040aab  mov     r12, r8
0x180040aae  mov     [rbp+arg_0], esi
0x180040ab1  mov     r13, rdx
0x180040ab4  mov     [rbp+var_10], rsi
0x180040ab8  mov     rbx, rcx
0x180040abb  mov     [rbp+var_18], rsi
0x180040abf  mov     [rbp+var_20], rsi
0x180040ac3  mov     [rbp+var_28], rsi
0x180040ac7  mov     [rbp+arg_18], esi
0x180040aca  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180040acf  mov     edi, eax
0x180040ad1  test    eax, eax
0x180040ad3  jns     short loc_180040B24
0x180040ad5  lea     rcx, aWiasgetchildre_0; "wiasGetChildrenContexts, invalid pParen"...
0x180040adc  call    WiaTrace_TraceLog
0x180040ae1  lea     rsi, aWiasgetchildre_5; "wiasGetChildrenContexts"
0x180040ae8  mov     rdx, rax; char *
0x180040aeb  mov     rcx, rsi; char *
0x180040aee  mov     rbx, rax
0x180040af1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180040af6  mov     rcx, rbx; this
0x180040af9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040afe  lea     rcx, aWiasgetchildre_0; "wiasGetChildrenContexts, invalid pParen"...
0x180040b05  call    WiaTrace_Trace
0x180040b0a  mov     r9d, 1; int
0x180040b10  mov     [rsp+60h+lpMem], rax; lpMem
0x180040b15  mov     r8, rsi; int
0x180040b18  call    WiaTrace_ProcessTrace_Ex
0x180040b1d  mov     eax, edi
0x180040b1f  jmp     loc_180040EC3
0x180040b24  test    rbx, rbx
0x180040b27  jz      loc_180040E76
0x180040b2d  test    r13, r13
0x180040b30  jz      loc_180040E76
0x180040b36  test    r12, r12
0x180040b39  jz      loc_180040E76
0x180040b3f  mov     [r13+0], esi
0x180040b43  lea     rcx, [rbx+28h]
0x180040b47  mov     [r12], rsi
0x180040b4b  lea     rdx, [rbp+arg_18]
0x180040b4f  mov     rax, [rcx]
0x180040b52  mov     r15, rsi
0x180040b55  mov     rax, [rax+28h]
0x180040b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b5e  mov     edi, eax
0x180040b60  test    eax, eax
0x180040b62  jns     short loc_180040BB5
0x180040b64  mov     edx, eax
0x180040b66  lea     rcx, aWiasgetchildre_4; "wiasGetChildrenContexts, GetItemType fa"...
0x180040b6d  call    WiaTrace_TraceLog
0x180040b72  lea     rsi, aWiasgetchildre_5; "wiasGetChildrenContexts"
0x180040b79  mov     rdx, rax; char *
0x180040b7c  mov     rcx, rsi; char *
0x180040b7f  mov     rbx, rax
0x180040b82  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180040b87  mov     rcx, rbx; this
0x180040b8a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040b8f  lea     rcx, aWiasgetchildre_4; "wiasGetChildrenContexts, GetItemType fa"...
0x180040b96  mov     edx, edi
0x180040b98  call    WiaTrace_Trace
0x180040b9d  mov     r9d, 1; int
0x180040ba3  mov     [rsp+60h+lpMem], rax; lpMem
0x180040ba8  mov     r8, rsi; int
0x180040bab  call    WiaTrace_ProcessTrace_Ex
0x180040bb0  jmp     loc_180040E15
0x180040bb5  cmp     [rbp+arg_18], 2
0x180040bb9  lea     rsi, aWiasgetchildre_5; "wiasGetChildrenContexts"
0x180040bc0  jnz     loc_180040C5C
0x180040bc6  lea     rcx, [rbx+38h]
0x180040bca  xor     edx, edx
0x180040bcc  mov     rax, [rcx]
0x180040bcf  lea     r8, [rbp+var_28]
0x180040bd3  mov     rax, [rax+28h]
0x180040bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bdc  mov     edi, eax
0x180040bde  test    eax, eax
0x180040be0  js      short loc_180040BF5
0x180040be2  mov     r8, [rbp+var_28]
0x180040be6  mov     eax, 80004003h
0x180040beb  test    r8, r8
0x180040bee  cmovz   edi, eax
0x180040bf1  test    edi, edi
0x180040bf3  jns     short loc_180040C46
0x180040bf5  mov     edx, edi
0x180040bf7  lea     rcx, aWiasgetchildre_6; "wiasGetChildrenContexts, IWiaItemX::Enu"...
0x180040bfe  call    WiaTrace_TraceLog
0x180040c03  mov     rdx, rax; char *
0x180040c06  mov     rcx, rsi; char *
0x180040c09  mov     rbx, rax
0x180040c0c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180040c11  mov     rcx, rbx; this
0x180040c14  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040c19  mov     edx, edi
0x180040c1b  lea     rcx, aWiasgetchildre_6; "wiasGetChildrenContexts, IWiaItemX::Enu"...
0x180040c22  call    WiaTrace_Trace
0x180040c27  mov     r9d, 1; int
0x180040c2d  mov     [rsp+60h+lpMem], rax; lpMem
0x180040c32  mov     r8, rsi; int
0x180040c35  call    WiaTrace_ProcessTrace_Ex
0x180040c3a  test    edi, edi
0x180040c3c  js      loc_180040E15
0x180040c42  mov     r8, [rbp+var_28]
0x180040c46  mov     rcx, [rbp+var_20]
0x180040c4a  cmp     [rbp+arg_18], 2
0x180040c4e  lea     rdx, [rbp+arg_0]
0x180040c52  jnz     short loc_180040C8E
0x180040c54  mov     rax, [r8]
0x180040c57  mov     rcx, r8
0x180040c5a  jmp     short loc_180040C91
0x180040c5c  mov     rax, [rbx]
0x180040c5f  lea     rdx, [rbp+var_20]
0x180040c63  mov     rcx, rbx
0x180040c66  mov     rax, [rax+28h]
0x180040c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c6f  mov     edi, eax
0x180040c71  test    eax, eax
0x180040c73  js      short loc_180040BF5
0x180040c75  mov     rcx, [rbp+var_20]
0x180040c79  test    rcx, rcx
0x180040c7c  jnz     short loc_180040C88
0x180040c7e  mov     edi, 80004003h
0x180040c83  jmp     loc_180040BF5
0x180040c88  mov     r8, [rbp+var_28]
0x180040c8c  jmp     short loc_180040C4A
0x180040c8e  mov     rax, [rcx]
0x180040c91  mov     rax, [rax+38h]
0x180040c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c9a  mov     edi, eax
0x180040c9c  test    eax, eax
0x180040c9e  jns     short loc_180040CD0
0x180040ca0  mov     edx, eax
0x180040ca2  lea     rcx, aWiasgetchildre_7; "wiasGetChildrenContexts, IEnumWiaItemX:"...
0x180040ca9  call    WiaTrace_TraceLog
0x180040cae  mov     rdx, rax; char *
0x180040cb1  mov     rcx, rsi; char *
0x180040cb4  mov     rbx, rax
0x180040cb7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180040cbc  mov     rcx, rbx; this
0x180040cbf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040cc4  lea     rcx, aWiasgetchildre_7; "wiasGetChildrenContexts, IEnumWiaItemX:"...
0x180040ccb  jmp     loc_180040B96
0x180040cd0  mov     eax, [rbp+arg_0]
0x180040cd3  test    eax, eax
0x180040cd5  jnz     short loc_180040D1F
0x180040cd7  lea     rdx, aWiasgetchildre_2; "wiasGetChildrenContexts, no children (S"...
0x180040cde  xor     ecx, ecx
0x180040ce0  call    WiaTrace_TraceLogWithSubComp
0x180040ce5  mov     rdx, rax; char *
0x180040ce8  mov     rcx, rsi; char *
0x180040ceb  mov     rbx, rax
0x180040cee  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180040cf3  mov     rcx, rbx; this
0x180040cf6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040cfb  lea     rdx, aWiasgetchildre_2; "wiasGetChildrenContexts, no children (S"...
0x180040d02  xor     ecx, ecx
0x180040d04  call    WiaTrace_TraceWithSubComp
0x180040d09  mov     r9d, 2; int
0x180040d0f  mov     [rsp+60h+lpMem], rax; lpMem
0x180040d14  mov     r8, rsi; int
0x180040d17  call    WiaTrace_ProcessTrace_Ex
0x180040d1c  mov     eax, [rbp+arg_0]
0x180040d1f  mov     ecx, eax
0x180040d21  shl     rcx, 3; cb
0x180040d25  call    cs:__imp_CoTaskMemAlloc
0x180040d2b  mov     r15, rax
0x180040d2e  test    rax, rax
0x180040d31  jnz     short loc_180040D7C
0x180040d33  lea     rcx, aWiasgetchildre_3; "wiasGetChildrenContexts, out of memory"
0x180040d3a  call    WiaTrace_TraceLog
0x180040d3f  mov     rdx, rax; char *
0x180040d42  mov     rcx, rsi; char *
0x180040d45  mov     rbx, rax
0x180040d48  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180040d4d  mov     rcx, rbx; this
0x180040d50  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040d55  lea     rcx, aWiasgetchildre_3; "wiasGetChildrenContexts, out of memory"
0x180040d5c  call    WiaTrace_Trace
0x180040d61  lea     r9d, [r15+1]; int
0x180040d65  mov     [rsp+60h+lpMem], rax; lpMem
0x180040d6a  mov     r8, rsi; int
0x180040d6d  call    WiaTrace_ProcessTrace_Ex
0x180040d72  mov     edi, 8007000Eh
0x180040d77  jmp     loc_180040E15
0x180040d7c  xor     ebx, ebx
0x180040d7e  cmp     [rbp+arg_18], 2
0x180040d82  mov     [rbp+var_30], ebx
0x180040d85  jnz     short loc_180040DC9
0x180040d87  mov     rcx, [rbp+var_28]
0x180040d8b  lea     r9, [rbp+var_30]
0x180040d8f  lea     r8, [rbp+var_18]
0x180040d93  mov     edx, 1
0x180040d98  mov     rax, [rcx]
0x180040d9b  mov     rax, [rax+18h]
0x180040d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040da4  test    eax, eax
0x180040da6  jnz     short loc_180040E0B
0x180040da8  cmp     ebx, [rbp+arg_0]
0x180040dab  jnb     short loc_180040E0B
0x180040dad  mov     rax, [rbp+var_18]
0x180040db1  mov     [r15+rbx*8], rax
0x180040db5  mov     rcx, [rbp+var_18]
0x180040db9  mov     rax, [rcx]
0x180040dbc  mov     rax, [rax+10h]
0x180040dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dc5  inc     ebx
0x180040dc7  jmp     short loc_180040D87
0x180040dc9  mov     rcx, [rbp+var_20]
0x180040dcd  lea     r9, [rbp+var_30]
0x180040dd1  lea     r8, [rbp+var_10]
0x180040dd5  mov     edx, 1
0x180040dda  mov     rax, [rcx]
0x180040ddd  mov     rax, [rax+18h]
0x180040de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040de6  test    eax, eax
0x180040de8  jnz     short loc_180040E0B
0x180040dea  cmp     ebx, [rbp+arg_0]
0x180040ded  jnb     short loc_180040E0B
0x180040def  mov     rax, [rbp+var_10]
0x180040df3  mov     [r15+rbx*8], rax
0x180040df7  mov     rcx, [rbp+var_10]
0x180040dfb  mov     rax, [rcx]
0x180040dfe  mov     rax, [rax+10h]
0x180040e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e07  inc     ebx
0x180040e09  jmp     short loc_180040DC9
0x180040e0b  mov     [r13+0], ebx
0x180040e0f  xor     edi, edi
0x180040e11  mov     [r12], r15
0x180040e15  cmp     [rbp+arg_18], 2
0x180040e19  jnz     short loc_180040E3A
0x180040e1b  mov     rcx, [rbp+var_28]
0x180040e1f  test    rcx, rcx
0x180040e22  jz      short loc_180040E57
0x180040e24  mov     rax, [rcx]
0x180040e27  mov     rax, [rax+10h]
0x180040e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e30  mov     [rbp+var_28], 0
0x180040e38  jmp     short loc_180040E57
0x180040e3a  mov     rcx, [rbp+var_20]
0x180040e3e  test    rcx, rcx
0x180040e41  jz      short loc_180040E57
0x180040e43  mov     rax, [rcx]
0x180040e46  mov     rax, [rax+10h]
0x180040e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e4f  mov     [rbp+var_20], 0
0x180040e57  test    edi, edi
0x180040e59  jns     loc_180040B1D
0x180040e5f  test    r15, r15
0x180040e62  jz      loc_180040B1D
0x180040e68  mov     rcx, r15; pv
0x180040e6b  call    cs:__imp_CoTaskMemFree
0x180040e71  jmp     loc_180040B1D
0x180040e76  lea     rcx, aWiasgetchildre_1; "wiasGetChildrenContexts, Invalid pointe"...
0x180040e7d  call    WiaTrace_TraceLog
0x180040e82  lea     rsi, aWiasgetchildre_5; "wiasGetChildrenContexts"
0x180040e89  mov     rdx, rax; char *
0x180040e8c  mov     rcx, rsi; char *
0x180040e8f  mov     rbx, rax
0x180040e92  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180040e97  mov     rcx, rbx; this
0x180040e9a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040e9f  lea     rcx, aWiasgetchildre_1; "wiasGetChildrenContexts, Invalid pointe"...
0x180040ea6  call    WiaTrace_Trace
0x180040eab  mov     r9d, 1; int
0x180040eb1  mov     [rsp+60h+lpMem], rax; lpMem
0x180040eb6  mov     r8, rsi; int
0x180040eb9  call    WiaTrace_ProcessTrace_Ex
0x180040ebe  mov     eax, 80004003h
0x180040ec3  lea     r11, [rsp+60h+var_s0]
0x180040ec8  mov     rbx, [r11+38h]
0x180040ecc  mov     rsi, [r11+40h]
0x180040ed0  mov     rsp, r11
0x180040ed3  pop     r15
0x180040ed5  pop     r13
0x180040ed7  pop     r12
0x180040ed9  pop     rdi
0x180040eda  pop     rbp
0x180040edb  retn
```
