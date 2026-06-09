# CFinishPage::_ShowError(long)

- ea: `0x18003fc94`
- end: `0x18003fe0e`
- name: `?_ShowError@CFinishPage@@AEAAXJ@Z`
- size: `378`
- prototype: `void __fastcall(CFinishPage *__hidden this, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f500`
- `0x18003f5f0`

## callees

- `0x180024948`
- `0x180026218`
- `0x18003d010`
- `0x18003fc94`
- `0x1800543a8`
- `0x180063bc8`
- `0x18007510c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fda0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fdfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fda0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fdfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fd21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fd21`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003fd6b`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003fd6b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003fd7d`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003fd97`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003fd7d`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003fd97`
- `DUI70!StrToID` at `0x18003fd39`
- `DUI70!StrToID` at `0x18003fd39`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fd45`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003fd45`

## pseudocode

```c
void __fastcall CFinishPage::_ShowError(CFinishPage *this, unsigned int a2)
{
  __int64 v3; // rdx
  unsigned __int16 *v4; // rdi
  __int64 v6; // r8
  const unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbx
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  struct DirectUI::Element *Descendent; // rax
  struct DirectUI::Element *v12; // rbx
  __int64 v13; // r8
  void *v14; // [rsp+20h] [rbp-10h]
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  int v16; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 *v17; // [rsp+68h] [rbp+38h] BYREF

  v3 = *((unsigned int *)this + 16);
  v4 = 0;
  v17 = 0;
  v16 = 0;
  LOBYTE(pv) = 0;
  if ( (int)MapError(a2, v3, &v16, &pv) < 0 )
  {
    v7 = (const unsigned __int16 *)ShellConstructMessageStringW(
                                     g_hinst,
                                     *((unsigned __int16 *)`CFinishPage::_ShowError'::`7'::sc_rguFinishPageGenericErrorText
                                     + 2 * *((int *)this + 16)));
    v8 = (unsigned __int16 *)v7;
    if ( !v7 )
      goto LABEL_6;
    CoAllocString(v7, &v17);
    LocalFree(v8);
  }
  else
  {
    TResourceStringAllocCopyEx<unsigned short *>(
      g_hinst,
      (unsigned int)v16,
      v6,
      (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
      v14,
      (char *)&v17);
  }
  v4 = v17;
LABEL_6:
  v9 = (DirectUI::Element *)*((_QWORD *)this + 17);
  v10 = StrToID(L"idErrorMessageText");
  Descendent = DirectUI::Element::FindDescendent(v9, v10);
  v12 = (struct DirectUI::Element *)element_cast<DirectUI::RichText>(Descendent);
  SetElementContentStringAndAccName(v12, v4);
  DirectUI::Element::SetClass(v12, L"error_text");
  DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 17), 3);
  DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 18), (_BYTE)pv != 0 ? -1 : -3);
  CoTaskMemFree(v4);
  pv = 0;
  if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
              g_hinst,
              3203,
              v13,
              (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
              v14,
              (char *)&pv) >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID, _QWORD))(**((_QWORD **)this + 3) + 24LL))(
      *((_QWORD *)this + 3),
      4,
      0,
      pv,
      0);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18003fc94  mov     [rsp-18h+arg_8], rbx
0x18003fc99  push    rbp
0x18003fc9a  push    rsi
0x18003fc9b  push    rdi
0x18003fc9c  mov     rbp, rsp
0x18003fc9f  sub     rsp, 30h
0x18003fca3  mov     ebx, edx
0x18003fca5  lea     r9, [rbp+pv]
0x18003fca9  mov     edx, [rcx+40h]
0x18003fcac  lea     r8, [rbp+arg_10]
0x18003fcb0  xor     edi, edi
0x18003fcb2  mov     rsi, rcx
0x18003fcb5  mov     ecx, ebx
0x18003fcb7  mov     [rbp+arg_18], rdi
0x18003fcbb  mov     [rbp+arg_10], edi
0x18003fcbe  mov     byte ptr [rbp+pv], dil
0x18003fcc2  call    ?MapError@@YAJJW4TASK_FLOW_ID@@PEAIPEA_N@Z; MapError(long,TASK_FLOW_ID,uint *,bool *)
0x18003fcc7  test    eax, eax
0x18003fcc9  js      short loc_18003FCEC
0x18003fccb  mov     edx, [rbp+arg_10]; int
0x18003fcce  lea     rax, [rbp+arg_18]
0x18003fcd2  mov     rcx, cs:g_hinst; int
0x18003fcd9  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18003fce0  mov     [rsp+30h+var_8], rax; void *
0x18003fce5  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18003fcea  jmp     short loc_18003FD27
0x18003fcec  movsxd  rax, dword ptr [rsi+40h]
0x18003fcf0  lea     rcx, ?sc_rguFinishPageGenericErrorText@?6??_ShowError@CFinishPage@@AEAAXJ@Z@4QBIB; uint const near * const `CFinishPage::_ShowError(long)'::`7'::sc_rguFinishPageGenericErrorText
0x18003fcf7  mov     r8d, ebx
0x18003fcfa  movzx   edx, word ptr [rcx+rax*4]
0x18003fcfe  mov     rcx, cs:g_hinst
0x18003fd05  call    ShellConstructMessageStringW
0x18003fd0a  mov     rbx, rax
0x18003fd0d  test    rax, rax
0x18003fd10  jz      short loc_18003FD2B
0x18003fd12  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18003fd16  mov     rcx, rax; unsigned __int16 *
0x18003fd19  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18003fd1e  mov     rcx, rbx; hMem
0x18003fd21  call    cs:__imp_LocalFree
0x18003fd27  mov     rdi, [rbp+arg_18]
0x18003fd2b  mov     rbx, [rsi+88h]
0x18003fd32  lea     rcx, aIderrormessage; "idErrorMessageText"
0x18003fd39  call    cs:__imp_StrToID
0x18003fd3f  movzx   edx, ax
0x18003fd42  mov     rcx, rbx
0x18003fd45  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003fd4b  mov     rcx, rax
0x18003fd4e  call    ??$element_cast@VRichText@DirectUI@@@@YAPEAVRichText@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::RichText>(DirectUI::Element *)
0x18003fd53  mov     rdx, rdi; unsigned __int16 *
0x18003fd56  mov     rcx, rax; struct DirectUI::Element *
0x18003fd59  mov     rbx, rax
0x18003fd5c  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003fd61  lea     rdx, aErrorText; "error_text"
0x18003fd68  mov     rcx, rbx
0x18003fd6b  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x18003fd71  mov     rcx, [rsi+88h]
0x18003fd78  mov     edx, 3
0x18003fd7d  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003fd83  mov     al, byte ptr [rbp+pv]
0x18003fd86  mov     rcx, [rsi+90h]
0x18003fd8d  neg     al
0x18003fd8f  sbb     edx, edx
0x18003fd91  and     edx, 2
0x18003fd94  add     edx, 0FFFFFFFDh
0x18003fd97  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003fd9d  mov     rcx, rdi; pv
0x18003fda0  call    cs:__imp_CoTaskMemFree
0x18003fda6  mov     rcx, cs:g_hinst; int
0x18003fdad  lea     rax, [rbp+pv]
0x18003fdb1  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18003fdb8  mov     [rsp+30h+var_8], rax; void *
0x18003fdbd  mov     edx, 0C83h; int
0x18003fdc2  mov     [rbp+pv], 0
0x18003fdca  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18003fdcf  test    eax, eax
0x18003fdd1  js      short loc_18003FE01
0x18003fdd3  mov     rcx, [rsi+18h]
0x18003fdd7  xor     r8d, r8d
0x18003fdda  mov     r9, [rbp+pv]
0x18003fdde  mov     [rsp+30h+var_10], 0
0x18003fde7  mov     rax, [rcx]
0x18003fdea  lea     edx, [r8+4]
0x18003fdee  mov     rax, [rax+18h]
0x18003fdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdf7  mov     rcx, [rbp+pv]; pv
0x18003fdfb  call    cs:__imp_CoTaskMemFree
0x18003fe01  mov     rbx, [rsp+30h+arg_8]
0x18003fe06  add     rsp, 30h
0x18003fe0a  pop     rdi
0x18003fe0b  pop     rsi
0x18003fe0c  pop     rbp
0x18003fe0d  retn
```
