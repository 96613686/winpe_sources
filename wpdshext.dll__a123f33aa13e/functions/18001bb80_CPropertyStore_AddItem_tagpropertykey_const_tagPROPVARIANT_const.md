# CPropertyStore::_AddItem(_tagpropertykey const &,tagPROPVARIANT const *)

- ea: `0x18001bb80`
- end: `0x18001bd87`
- name: `?_AddItem@CPropertyStore@@AEAAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z`
- size: `519`
- prototype: `int(CPropertyStore *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a630`

## callees

- `0x18001bb80`
- `0x18001f680`
- `0x180022c04`
- `0x18002e0d8`
- `0x18002ff5c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001bd38`
- `KERNEL32!GetLastError` at `0x18001bd38`
- `KERNEL32!HeapAlloc` at `0x18001bbc6`
- `KERNEL32!HeapAlloc` at `0x18001bbc6`
- `KERNEL32!GetProcessHeap` at `0x18001bbb2`
- `KERNEL32!GetProcessHeap` at `0x18001bbb2`
- `KERNEL32!DeactivateActCtx` at `0x18001bd47`
- `KERNEL32!DeactivateActCtx` at `0x18001bd6e`
- `KERNEL32!DeactivateActCtx` at `0x18001bd47`
- `KERNEL32!DeactivateActCtx` at `0x18001bd6e`
- `KERNEL32!SetLastError` at `0x18001bd4f`
- `KERNEL32!SetLastError` at `0x18001bd4f`
- `ole32!PropVariantCopy` at `0x18001bbf7`
- `ole32!PropVariantCopy` at `0x18001bbf7`

## pseudocode

```c
__int64 __fastcall CPropertyStore::_AddItem(
        CPropertyStore *this,
        const struct _tagpropertykey *a2,
        const struct tagPROPVARIANT *a3)
{
  DWORD pid; // eax
  HANDLE ProcessHeap; // rax
  PROPVARIANT *v8; // rax
  PROPERTY_ITEM *v9; // rdi
  unsigned int v10; // edx
  unsigned int v11; // ebp
  unsigned int (__fastcall *v12)(__int64, __int64, PROPERTY_ITEM *); // rbx
  __int64 v13; // rsi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  pid = a2->pid;
  if ( pid == 3 )
  {
    v16 = *(_QWORD *)&PKEY_Capacity.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
    if ( *(_QWORD *)&PKEY_Capacity.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
      v16 = *(_QWORD *)PKEY_Capacity.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
    if ( v16 )
      goto LABEL_3;
  }
  else
  {
    if ( pid != 2 )
      goto LABEL_3;
    v15 = *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
    if ( *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
      v15 = *(_QWORD *)PKEY_FreeSpace.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
    if ( v15 )
      goto LABEL_3;
  }
  if ( a3->hVal.QuadPart == -1 )
    return 1;
LABEL_3:
  ProcessHeap = GetProcessHeap();
  v8 = (PROPVARIANT *)HeapAlloc(ProcessHeap, 8u, 0x30u);
  v9 = (PROPERTY_ITEM *)v8;
  if ( v8 )
  {
    *(_OWORD *)&v8[1].vt = 0;
    v8[1].bstrblobVal.pData = 0;
    *(GUID *)&v8->vt = a2->fmtid;
    *((_DWORD *)&v8->decVal + 4) = a2->pid;
    v11 = PropVariantCopy(v8 + 1, a3);
    if ( (v11 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v11);
      goto LABEL_28;
    }
    v12 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))`IsolationAwareDPA_InsertPtr'::`2'::s_pfn;
    v13 = *((_QWORD *)this + 14);
    if ( `IsolationAwareDPA_InsertPtr'::`2'::s_pfn )
      goto LABEL_6;
    ulCookie = 0;
    if ( IsolationAwarePrivateT_SAbnPgpgk
      || IsolationAwarePrivateT_SqbjaYRiRY
      || (unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
    {
      v17 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DPA_InsertPtr");
      v12 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))v17;
      if ( IsolationAwarePrivateT_SqbjaYRiRY )
      {
        if ( !v17 )
          goto LABEL_27;
      }
      else
      {
        if ( !v17 )
        {
          LastError = GetLastError();
          DeactivateActCtx(0, ulCookie);
          SetLastError(LastError);
          goto LABEL_27;
        }
        DeactivateActCtx(0, ulCookie);
      }
      `IsolationAwareDPA_InsertPtr'::`2'::s_pfn = (__int64)v12;
LABEL_6:
      if ( v12(v13, 0x7FFFFFFF, v9) != -1 )
        return v11;
    }
LABEL_27:
    v11 = -2147467259;
LABEL_28:
    PROPERTY_ITEM::`scalar deleting destructor'(v9, v10);
    return v11;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001bb80  mov     [rsp+arg_10], rbx
0x18001bb85  mov     [rsp+arg_18], rbp
0x18001bb8a  push    rsi
0x18001bb8b  sub     rsp, 20h
0x18001bb8f  mov     eax, [rdx+10h]
0x18001bb92  mov     rbp, r8
0x18001bb95  mov     rbx, rdx
0x18001bb98  mov     rsi, rcx
0x18001bb9b  cmp     eax, 3
0x18001bb9e  jz      loc_18001BC70
0x18001bba4  cmp     eax, 2
0x18001bba7  jz      loc_18001BC4E
0x18001bbad  mov     [rsp+28h+arg_0], rdi
0x18001bbb2  call    cs:__imp_GetProcessHeap
0x18001bbb8  mov     edx, 8; dwFlags
0x18001bbbd  mov     r8d, 30h ; '0'; dwBytes
0x18001bbc3  mov     rcx, rax; hHeap
0x18001bbc6  call    cs:__imp_HeapAlloc
0x18001bbcc  mov     rdi, rax
0x18001bbcf  test    rax, rax
0x18001bbd2  jz      loc_18001BCB0
0x18001bbd8  lea     rcx, [rax+18h]; pvarDest
0x18001bbdc  xorps   xmm0, xmm0
0x18001bbdf  movups  xmmword ptr [rcx], xmm0
0x18001bbe2  xor     eax, eax
0x18001bbe4  mov     [rcx+10h], rax
0x18001bbe8  movups  xmm0, xmmword ptr [rbx]
0x18001bbeb  movups  xmmword ptr [rdi], xmm0
0x18001bbee  mov     edx, [rbx+10h]
0x18001bbf1  mov     [rdi+10h], edx
0x18001bbf4  mov     rdx, rbp; pvarSrc
0x18001bbf7  call    cs:__imp_PropVariantCopy
0x18001bbfd  mov     ebp, eax
0x18001bbff  test    eax, eax
0x18001bc01  js      loc_18001BCB7
0x18001bc07  mov     rbx, cs:?s_pfn@?1??IsolationAwareDPA_InsertPtr@@9@4P6AHPEAU_DPA@@HPEAX@ZEA; int (*`IsolationAwareDPA_InsertPtr'::`2'::s_pfn)(_DPA *,int,void *)
0x18001bc0e  mov     rsi, [rsi+70h]
0x18001bc12  test    rbx, rbx
0x18001bc15  jz      loc_18001BCF2
0x18001bc1b  mov     r8, rdi
0x18001bc1e  mov     edx, 7FFFFFFFh
0x18001bc23  mov     rcx, rsi
0x18001bc26  mov     rax, rbx
0x18001bc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc2e  cmp     eax, 0FFFFFFFFh
0x18001bc31  jz      loc_18001BD55
0x18001bc37  mov     eax, ebp
0x18001bc39  mov     rdi, [rsp+28h+arg_0]
0x18001bc3e  mov     rbx, [rsp+28h+arg_10]
0x18001bc43  mov     rbp, [rsp+28h+arg_18]
0x18001bc48  add     rsp, 20h
0x18001bc4c  pop     rsi
0x18001bc4d  retn
0x18001bc4e  mov     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data1
0x18001bc55  sub     rax, [rdx]
0x18001bc58  jnz     short loc_18001BC65
0x18001bc5a  mov     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data4
0x18001bc61  sub     rax, [rdx+8]
0x18001bc65  test    rax, rax
0x18001bc68  jnz     loc_18001BBAD
0x18001bc6e  jmp     short loc_18001BC90
0x18001bc70  mov     rax, qword ptr cs:PKEY_Capacity.fmtid.Data1
0x18001bc77  sub     rax, [rdx]
0x18001bc7a  jnz     short loc_18001BC87
0x18001bc7c  mov     rax, qword ptr cs:PKEY_Capacity.fmtid.Data4
0x18001bc83  sub     rax, [rdx+8]
0x18001bc87  test    rax, rax
0x18001bc8a  jnz     loc_18001BBAD
0x18001bc90  cmp     qword ptr [r8+8], 0FFFFFFFFFFFFFFFFh
0x18001bc95  jnz     loc_18001BBAD
0x18001bc9b  mov     rbx, [rsp+28h+arg_10]
0x18001bca0  mov     eax, 1
0x18001bca5  mov     rbp, [rsp+28h+arg_18]
0x18001bcaa  add     rsp, 20h
0x18001bcae  pop     rsi
0x18001bcaf  retn
0x18001bcb0  mov     eax, 8007000Eh
0x18001bcb5  jmp     short loc_18001BC39
0x18001bcb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcbe  lea     rax, WPP_GLOBAL_Control
0x18001bcc5  cmp     rcx, rax
0x18001bcc8  jz      loc_18001BD5A
0x18001bcce  test    byte ptr [rcx+1Ch], 2
0x18001bcd2  jz      loc_18001BD5A
0x18001bcd8  mov     rcx, [rcx+10h]
0x18001bcdc  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18001bce3  mov     edx, 2Eh ; '.'
0x18001bce8  mov     r9d, ebp
0x18001bceb  call    WPP_SF_d
0x18001bcf0  jmp     short loc_18001BD5A
0x18001bcf2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001bcf9  mov     [rsp+28h+ulCookie], 0
0x18001bd02  jnz     short loc_18001BD1B
0x18001bd04  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001bd0b  jnz     short loc_18001BD1B
0x18001bd0d  lea     rcx, [rsp+28h+ulCookie]; lpCookie
0x18001bd12  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001bd17  test    eax, eax
0x18001bd19  jz      short loc_18001BD55
0x18001bd1b  lea     rcx, aDpaInsertptr; "DPA_InsertPtr"
0x18001bd22  call    Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001bd27  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001bd2e  mov     rbx, rax
0x18001bd31  jnz     short loc_18001BD76
0x18001bd33  test    rax, rax
0x18001bd36  jnz     short loc_18001BD67
0x18001bd38  call    cs:__imp_GetLastError
0x18001bd3e  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001bd43  xor     ecx, ecx; dwFlags
0x18001bd45  mov     ebx, eax
0x18001bd47  call    cs:__imp_DeactivateActCtx
0x18001bd4d  mov     ecx, ebx; dwErrCode
0x18001bd4f  call    cs:__imp_SetLastError
0x18001bd55  mov     ebp, 80004005h
0x18001bd5a  mov     rcx, rdi; this
0x18001bd5d  call    ??_GPROPERTY_ITEM@@QEAAPEAXI@Z; PROPERTY_ITEM::`scalar deleting destructor'(uint)
0x18001bd62  jmp     loc_18001BC37
0x18001bd67  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001bd6c  xor     ecx, ecx; dwFlags
0x18001bd6e  call    cs:__imp_DeactivateActCtx
0x18001bd74  jmp     short loc_18001BD7B
0x18001bd76  test    rbx, rbx
0x18001bd79  jz      short loc_18001BD55
0x18001bd7b  mov     cs:?s_pfn@?1??IsolationAwareDPA_InsertPtr@@9@4P6AHPEAU_DPA@@HPEAX@ZEA, rbx; int (*`IsolationAwareDPA_InsertPtr'::`2'::s_pfn)(_DPA *,int,void *)
0x18001bd82  jmp     loc_18001BC1B
```
