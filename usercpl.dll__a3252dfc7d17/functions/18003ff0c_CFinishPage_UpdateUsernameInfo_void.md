# CFinishPage::_UpdateUsernameInfo(void)

- ea: `0x18003ff0c`
- end: `0x1800400a1`
- name: `?_UpdateUsernameInfo@CFinishPage@@AEAAXXZ`
- size: `405`
- prototype: `void __fastcall(CFinishPage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003f5f0`

## callees

- `0x180026218`
- `0x18003ff0c`
- `0x180063bc8`
- `0x180069578`
- `0x18007510c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040093`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180040015`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180040033`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004007f`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180040015`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180040033`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004007f`

## pseudocode

```c
void __fastcall CFinishPage::_UpdateUsernameInfo(CFinishPage *this)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rcx
  CUserNameFormat *v5; // rcx
  __int64 v6; // r8
  struct DirectUI::Element *v7; // rdi
  __int64 v8; // rcx
  bool *v9; // [rsp+20h] [rbp-10h]
  unsigned __int16 *v10; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v11; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF

  v10 = 0;
  v2 = *((_QWORD *)this + 9);
  v11 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v2 + 48LL))(v2, &v11);
  v4 = *((_QWORD *)this + 9);
  if ( v3 < 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v4 + 40LL))(v4, &v10);
  }
  else
  {
    pv = 0;
    (*(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v4 + 56LL))(v4, &pv);
    if ( pv )
      CUserNameFormat::FormatDisplayName(v5, v11, (const unsigned __int16 *)pv, &v10, v9);
    else
      CoAllocString(v11, &v10);
    CoTaskMemFree(pv);
    CoTaskMemFree(v11);
    v11 = 0;
  }
  if ( v10 )
    SetElementContentStringAndAccName(*((struct DirectUI::Element **)this + 12), v10);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 72LL))(*((_QWORD *)this + 9)) - 2 <= 1 )
  {
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 13), -3);
    v7 = *(struct DirectUI::Element **)((char *)this + (v10 != 0 ? 8 : 0) + 96);
    v8 = *((_QWORD *)this + 9);
    pv = 0;
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 64LL))(v8, &pv) >= 0 )
    {
      SetElementContentStringAndAccName(v7, (const unsigned __int16 *)pv);
      DirectUI::Element::SetLayoutPos(v7, 1);
      goto LABEL_14;
    }
  }
  else
  {
    pv = 0;
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
                g_hinst,
                3262,
                v6,
                (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
                v9,
                (char *)&pv) >= 0 )
    {
      DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 13), 1);
      SetElementContentStringAndAccName(*((struct DirectUI::Element **)this + 13), (const unsigned __int16 *)pv);
LABEL_14:
      CoTaskMemFree(pv);
    }
  }
  CoTaskMemFree(v10);
}

```

## disassembly

```asm
0x18003ff0c  push    rbp
0x18003ff0e  push    rbx
0x18003ff0f  push    rdi
0x18003ff10  mov     rbp, rsp
0x18003ff13  sub     rsp, 30h
0x18003ff17  mov     rbx, rcx
0x18003ff1a  mov     [rbp+arg_0], 0
0x18003ff22  mov     rcx, [rcx+48h]
0x18003ff26  lea     rdx, [rbp+arg_8]
0x18003ff2a  mov     [rbp+arg_8], 0
0x18003ff32  mov     rax, [rcx]
0x18003ff35  mov     rax, [rax+30h]
0x18003ff39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff3e  mov     rcx, [rbx+48h]
0x18003ff42  test    eax, eax
0x18003ff44  js      short loc_18003FFA1
0x18003ff46  mov     [rbp+pv], 0
0x18003ff4e  lea     rdx, [rbp+pv]
0x18003ff52  mov     rax, [rcx]
0x18003ff55  mov     rax, [rax+38h]
0x18003ff59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff5e  mov     r8, [rbp+pv]; unsigned __int16 *
0x18003ff62  test    r8, r8
0x18003ff65  jz      short loc_18003FF76
0x18003ff67  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18003ff6b  lea     r9, [rbp+arg_0]; unsigned __int16 **
0x18003ff6f  call    ?FormatDisplayName@CUserNameFormat@@QEAAJPEBG0PEAPEAGPEA_N@Z; CUserNameFormat::FormatDisplayName(ushort const *,ushort const *,ushort * *,bool *)
0x18003ff74  jmp     short loc_18003FF83
0x18003ff76  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x18003ff7a  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x18003ff7e  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18003ff83  mov     rcx, [rbp+pv]; pv
0x18003ff87  call    cs:__imp_CoTaskMemFree
0x18003ff8d  mov     rcx, [rbp+arg_8]; pv
0x18003ff91  call    cs:__imp_CoTaskMemFree
0x18003ff97  mov     [rbp+arg_8], 0
0x18003ff9f  jmp     short loc_18003FFB1
0x18003ffa1  mov     rax, [rcx]
0x18003ffa4  lea     rdx, [rbp+arg_0]
0x18003ffa8  mov     rax, [rax+28h]
0x18003ffac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffb1  mov     rdx, [rbp+arg_0]; unsigned __int16 *
0x18003ffb5  test    rdx, rdx
0x18003ffb8  jz      short loc_18003FFC3
0x18003ffba  mov     rcx, [rbx+60h]; struct DirectUI::Element *
0x18003ffbe  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003ffc3  mov     rcx, [rbx+48h]
0x18003ffc7  mov     rax, [rcx]
0x18003ffca  mov     rax, [rax+48h]
0x18003ffce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffd3  add     eax, 0FFFFFFFEh
0x18003ffd6  cmp     eax, 1
0x18003ffd9  jbe     short loc_18004002A
0x18003ffdb  mov     rcx, cs:g_hinst; int
0x18003ffe2  lea     rax, [rbp+pv]
0x18003ffe6  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18003ffed  mov     [rsp+30h+var_8], rax; void *
0x18003fff2  mov     edx, 0CBEh; int
0x18003fff7  mov     [rbp+pv], 0
0x18003ffff  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180040004  test    eax, eax
0x180040006  js      loc_18004008F
0x18004000c  mov     rcx, [rbx+68h]
0x180040010  mov     edx, 1
0x180040015  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18004001b  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18004001f  mov     rcx, [rbx+68h]; struct DirectUI::Element *
0x180040023  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x180040028  jmp     short loc_180040085
0x18004002a  mov     rcx, [rbx+68h]
0x18004002e  mov     edx, 0FFFFFFFDh
0x180040033  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180040039  mov     rax, [rbp+arg_0]
0x18004003d  lea     rdx, [rbp+pv]
0x180040041  neg     rax
0x180040044  sbb     rcx, rcx
0x180040047  and     ecx, 8
0x18004004a  mov     rdi, [rcx+rbx+60h]
0x18004004f  mov     rcx, [rbx+48h]
0x180040053  mov     [rbp+pv], 0
0x18004005b  mov     rax, [rcx]
0x18004005e  mov     rax, [rax+40h]
0x180040062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040067  test    eax, eax
0x180040069  js      short loc_18004008F
0x18004006b  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18004006f  mov     rcx, rdi; struct DirectUI::Element *
0x180040072  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x180040077  mov     edx, 1
0x18004007c  mov     rcx, rdi
0x18004007f  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180040085  mov     rcx, [rbp+pv]; pv
0x180040089  call    cs:__imp_CoTaskMemFree
0x18004008f  mov     rcx, [rbp+arg_0]; pv
0x180040093  call    cs:__imp_CoTaskMemFree
0x180040099  add     rsp, 30h
0x18004009d  pop     rdi
0x18004009e  pop     rbx
0x18004009f  pop     rbp
0x1800400a0  retn
```
