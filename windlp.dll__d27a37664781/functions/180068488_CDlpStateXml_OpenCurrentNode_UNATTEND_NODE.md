# CDlpStateXml::OpenCurrentNode(_UNATTEND_NODE *)

- ea: `0x180068488`
- end: `0x18006858c`
- name: `?OpenCurrentNode@CDlpStateXml@@AEAAJPEAU_UNATTEND_NODE@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this, struct _UNATTEND_NODE *)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004c5c0`
- `0x18005b7d0`
- `0x18005e3a0`
- `0x18005f440`
- `0x180068350`
- `0x180068488`
- `0x180073750`
- `0x180074cd0`
- `0x180075c10`

## callees

- `0x18000aba4`
- `0x18001fd60`
- `0x180028640`
- `0x180068488`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068565`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068565`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068574`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068574`
- `UNATTEND!UnattendFreeNode` at `0x180068552`
- `UNATTEND!UnattendFreeNode` at `0x180068552`
- `UNATTEND!UnattendCtxOpenNode` at `0x18006853a`
- `UNATTEND!UnattendCtxOpenNode` at `0x18006853a`
- `UNATTEND!UnattendCtxOpenNodeByNode` at `0x18006851d`
- `UNATTEND!UnattendCtxOpenNodeByNode` at `0x18006851d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpStateXml::OpenCurrentNode(CDlpStateXml *this, struct _UNATTEND_NODE *a2)
{
  unsigned __int16 *v4; // rbx
  CDlpStateXml *v5; // rcx
  int v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  HANDLE ProcessHeap; // rax
  _OWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v12; // [rsp+50h] [rbp-38h]
  unsigned __int16 *v13; // [rsp+90h] [rbp+8h] BYREF

  v4 = 0;
  v13 = 0;
  memset(v11, 0, sizeof(v11));
  v12 = 0;
  v5 = (CDlpStateXml *)*((_QWORD *)this + 15);
  if ( !v5 )
  {
    v6 = UnattendCtxOpenNode(*((_QWORD *)this + 16), *((_QWORD *)this + 12), a2);
    goto LABEL_7;
  }
  v6 = CDlpStateXml::OpenCurrentNode(v5, (struct _UNATTEND_NODE *)v11);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = STRAPI_Format(&v13, L"%s[*]", *((_QWORD *)this + 12));
    v7 = v8;
    if ( v8 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
      v4 = v13;
      goto LABEL_9;
    }
    v4 = v13;
    v6 = UnattendCtxOpenNodeByNode(*((_QWORD *)this + 16), v11, v13, a2, *((_DWORD *)this + 36));
LABEL_7:
    v7 = v6;
    if ( v6 >= 0 )
      goto LABEL_9;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
LABEL_9:
  UnattendFreeNode(v11);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x180068488  mov     r11, rsp
0x18006848b  push    rbx
0x18006848c  push    rbp
0x18006848d  push    rsi
0x18006848e  push    rdi
0x18006848f  sub     rsp, 68h
0x180068493  mov     rbp, rdx
0x180068496  mov     rsi, rcx
0x180068499  xor     ebx, ebx
0x18006849b  mov     [r11+8], rbx
0x18006849f  xorps   xmm0, xmm0
0x1800684a2  xor     eax, eax
0x1800684a4  movups  [rsp+88h+var_58], xmm0
0x1800684a9  movups  [rsp+88h+var_48], xmm0
0x1800684ae  mov     [r11-38h], rax
0x1800684b2  mov     rcx, [rcx+78h]; this
0x1800684b6  test    rcx, rcx
0x1800684b9  jz      short loc_180068525
0x1800684bb  lea     rdx, [r11-58h]; struct _UNATTEND_NODE *
0x1800684bf  call    ?OpenCurrentNode@CDlpStateXml@@AEAAJPEAU_UNATTEND_NODE@@@Z; CDlpStateXml::OpenCurrentNode(_UNATTEND_NODE *)
0x1800684c4  mov     edi, eax
0x1800684c6  test    eax, eax
0x1800684c8  js      short loc_180068546
0x1800684ca  mov     r8, [rsi+60h]
0x1800684ce  lea     rdx, aS_0; "%s[*]"
0x1800684d5  lea     rcx, [rsp+88h+arg_0]; unsigned __int16 **
0x1800684dd  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1800684e2  mov     edi, eax
0x1800684e4  test    eax, eax
0x1800684e6  jns     short loc_1800684F9
0x1800684e8  mov     ecx, eax
0x1800684ea  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800684ef  mov     rbx, [rsp+88h+arg_0]
0x1800684f7  jmp     short loc_18006854D
0x1800684f9  mov     eax, [rsi+90h]
0x1800684ff  mov     rbx, [rsp+88h+arg_0]
0x180068507  mov     [rsp+88h+var_68], eax
0x18006850b  mov     r9, rbp
0x18006850e  mov     r8, rbx
0x180068511  lea     rdx, [rsp+88h+var_58]
0x180068516  mov     rcx, [rsi+80h]
0x18006851d  call    cs:__imp_UnattendCtxOpenNodeByNode
0x180068523  jmp     short loc_180068540
0x180068525  mov     r9d, [rsi+90h]
0x18006852c  mov     r8, rbp
0x18006852f  mov     rdx, [rsi+60h]
0x180068533  mov     rcx, [rsi+80h]
0x18006853a  call    cs:__imp_UnattendCtxOpenNode
0x180068540  test    eax, eax
0x180068542  mov     edi, eax
0x180068544  jns     short loc_18006854D
0x180068546  mov     ecx, eax
0x180068548  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006854d  lea     rcx, [rsp+88h+var_58]
0x180068552  call    cs:__imp_UnattendFreeNode
0x180068558  mov     ecx, edi
0x18006855a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006855f  nop
0x180068560  test    rbx, rbx
0x180068563  jz      short loc_180068581
0x180068565  call    cs:__imp_GetProcessHeap
0x18006856b  mov     rcx, rax; hHeap
0x18006856e  lea     r8, [rbx-4]; lpMem
0x180068572  xor     edx, edx; dwFlags
0x180068574  call    cs:__imp_HeapFree
0x18006857a  xor     ecx, ecx
0x18006857c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180068581  mov     eax, edi
0x180068583  add     rsp, 68h
0x180068587  pop     rdi
0x180068588  pop     rsi
0x180068589  pop     rbp
0x18006858a  pop     rbx
0x18006858b  retn
```
