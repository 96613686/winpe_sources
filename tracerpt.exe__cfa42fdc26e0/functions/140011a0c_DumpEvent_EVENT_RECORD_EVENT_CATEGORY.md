# DumpEvent(_EVENT_RECORD *,EVENT_CATEGORY)

- ea: `0x140011a0c`
- end: `0x140011c6c`
- name: `?DumpEvent@@YAXPEAU_EVENT_RECORD@@W4EVENT_CATEGORY@@@Z`
- size: `608`
- prototype: `void __fastcall(struct _EVENT_RECORD *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140003a30`

## callees

- `0x140004afc`
- `0x140004cac`
- `0x140004f08`
- `0x14000d4a8`
- `0x14000d598`
- `0x140011980`
- `0x140011a0c`
- `0x140011f98`
- `0x140013a78`
- `0x140015fa0`
- `0x140016130`
- `0x14002e0b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011c2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011c2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c4b`
- `wevtapi!EvtIntWriteXmlEventToLocalLogfile` at `0x140011c43`
- `wevtapi!EvtIntWriteXmlEventToLocalLogfile` at `0x140011c43`

## pseudocode

```c
void __fastcall DumpEvent(struct _EVENT_RECORD *a1, int a2)
{
  struct _MOF_INFO *MofInfoHead; // rax
  struct _MOF_INFO *v5; // rdi
  char v6; // si
  _DWORD *v7; // rax
  struct _MOF_VERSION *MofVersion; // rax
  struct _MOF_VERSION *v9; // r14
  LPVOID v10; // rcx
  int v11; // eax
  struct _MOF_COUNT *MofCount; // rax
  int v13; // eax
  struct _iobuf *v14; // rdi
  int v15; // eax
  int v16; // r8d
  __int64 v17; // rbp
  __int64 v18; // rax
  __int64 v19; // rcx
  void *v20; // rsi
  __int64 v21; // rbx
  HANDLE ProcessHeap; // rax
  int v23; // [rsp+40h] [rbp+8h] BYREF
  int v24; // [rsp+50h] [rbp+18h] BYREF

  if ( a1 && (a1->UserData || !a1->UserDataLength) )
  {
    MofInfoHead = GetMofInfoHead(&a1->EventHeader.ProviderId);
    v5 = MofInfoHead;
    if ( MofInfoHead )
    {
      v6 = 1;
      ++*((_DWORD *)MofInfoHead + 10);
      *((_WORD *)MofInfoHead + 3124) = a1->EventHeader.Flags;
      v7 = g_TraceContext;
      if ( (*((_BYTE *)g_TraceContext + 6416) & 8) != 0 && !a2 )
        ++*((_DWORD *)v5 + 11);
      if ( (v7[1604] & 0x400) != 0 && (a1->EventHeader.Flags & 0x100) == 0 )
        byte_1400820CB = 1;
      MofVersion = GetMofVersion(a1, v5, 0);
      v9 = MofVersion;
      if ( MofVersion )
      {
        v10 = g_TraceContext;
        if ( (*((_DWORD *)g_TraceContext + 1604) & 0x4000000) != 0 && !a2 )
        {
          StoreEvent(a1, v5, MofVersion);
          v10 = g_TraceContext;
        }
        v11 = *((_DWORD *)v10 + 1604);
        if ( (v11 & 0x400) != 0 || (v11 & 8) != 0 && !a2 )
        {
          MofCount = GetMofCount(a1, v5, v9);
          if ( !MofCount )
            return;
          v10 = g_TraceContext;
          if ( (*((_DWORD *)g_TraceContext + 1604) & 0x400) != 0 )
            ++*((_DWORD *)MofCount + 4);
          if ( (*((_BYTE *)v10 + 6416) & 8) != 0 && !a2 )
            ++*((_DWORD *)MofCount + 5);
        }
        v13 = *((_DWORD *)v10 + 1604);
        if ( (v13 & 0x80u) != 0 )
        {
          if ( (v13 & 0x12000000) != 0 )
          {
            v14 = (struct _iobuf *)OpenTempFile();
            if ( !v14 )
              return;
            v10 = g_TraceContext;
          }
          else
          {
            v14 = (struct _iobuf *)*((_QWORD *)v10 + 799);
          }
          v15 = *((_DWORD *)v10 + 1604);
          if ( (v15 & 0x3000000) != 0 || (v15 & 0x8000000) != 0 || (v15 & 0x10000000) != 0 )
          {
            if ( (v15 & 0x8000000) != 0 || (v15 & 0x10000000) != 0 )
            {
              v16 = 1;
              goto LABEL_38;
            }
          }
          else
          {
            v6 = 0;
          }
          v16 = 0;
          if ( !v6 )
          {
            DumpEventIntoCSV(v14, a1);
            goto LABEL_39;
          }
LABEL_38:
          DumpEventIntoXML(v14, a1, v16);
LABEL_39:
          if ( (*((_DWORD *)g_TraceContext + 1604) & 0x12000000) != 0 )
          {
            TracerptFPutc(0, v14);
            v24 = 0;
            v23 = 0;
            v17 = *((_QWORD *)g_TraceContext + 1088);
            v18 = ReadTempFile(v14, &v23);
            v20 = (void *)v18;
            if ( !v18 )
              goto LABEL_45;
            v21 = ConvertMultiByteToWideChar(v19, v18, &v24);
            if ( v14[1365]._file )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v20);
            }
            if ( v21 )
              EvtIntWriteXmlEventToLocalLogfile(v17, v21, 0);
            else
LABEL_45:
              GetLastError();
            TracerptFClose(v14);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140011a0c  test    rcx, rcx
0x140011a0f  jz      locret_140011C6B
0x140011a15  mov     [rsp+arg_8], rbx
0x140011a1a  mov     [rsp+arg_18], rbp
0x140011a1f  push    rsi
0x140011a20  push    rdi
0x140011a21  push    r14
0x140011a23  sub     rsp, 20h
0x140011a27  cmp     qword ptr [rcx+60h], 0
0x140011a2c  mov     ebp, edx
0x140011a2e  mov     rbx, rcx
0x140011a31  jnz     short loc_140011A3F
0x140011a33  xor     eax, eax
0x140011a35  cmp     ax, [rcx+56h]
0x140011a39  jnz     loc_140011C59
0x140011a3f  add     rcx, 18h; struct _GUID *
0x140011a43  call    ?GetMofInfoHead@@YAPEAU_MOF_INFO@@PEBU_GUID@@@Z; GetMofInfoHead(_GUID const *)
0x140011a48  mov     rdi, rax
0x140011a4b  test    rax, rax
0x140011a4e  jz      loc_140011C59
0x140011a54  mov     esi, 1
0x140011a59  add     [rax+28h], esi
0x140011a5c  movzx   ecx, word ptr [rbx+4]
0x140011a60  mov     [rax+1868h], cx
0x140011a67  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140011a6e  test    byte ptr [rax+1910h], 8
0x140011a75  jz      short loc_140011A7E
0x140011a77  test    ebp, ebp
0x140011a79  jnz     short loc_140011A7E
0x140011a7b  add     [rdi+2Ch], esi
0x140011a7e  test    dword ptr [rax+1910h], 400h
0x140011a88  jz      short loc_140011A9C
0x140011a8a  mov     eax, 100h
0x140011a8f  test    [rbx+4], ax
0x140011a93  jnz     short loc_140011A9C
0x140011a95  mov     cs:byte_1400820CB, sil
0x140011a9c  xor     r8d, r8d; unsigned __int8
0x140011a9f  mov     rdx, rdi; struct _MOF_INFO *
0x140011aa2  mov     rcx, rbx; Event
0x140011aa5  call    ?GetMofVersion@@YAPEAU_MOF_VERSION@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@E@Z; GetMofVersion(_EVENT_RECORD *,_MOF_INFO *,uchar)
0x140011aaa  mov     r14, rax
0x140011aad  test    rax, rax
0x140011ab0  jz      loc_140011C59
0x140011ab6  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140011abd  test    dword ptr [rcx+1910h], 4000000h
0x140011ac7  jz      short loc_140011AE2
0x140011ac9  test    ebp, ebp
0x140011acb  jnz     short loc_140011AE2
0x140011acd  mov     r8, rax; struct _MOF_VERSION *
0x140011ad0  mov     rdx, rdi; struct _MOF_INFO *
0x140011ad3  mov     rcx, rbx; struct _EVENT_RECORD *
0x140011ad6  call    ?StoreEvent@@YAXPEAU_EVENT_RECORD@@PEAU_MOF_INFO@@PEAU_MOF_VERSION@@@Z; StoreEvent(_EVENT_RECORD *,_MOF_INFO *,_MOF_VERSION *)
0x140011adb  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140011ae2  mov     eax, [rcx+1910h]
0x140011ae8  bt      eax, 0Ah
0x140011aec  jb      short loc_140011AF6
0x140011aee  test    al, 8
0x140011af0  jz      short loc_140011B33
0x140011af2  test    ebp, ebp
0x140011af4  jnz     short loc_140011B33
0x140011af6  mov     r8, r14; struct _MOF_VERSION *
0x140011af9  mov     rdx, rdi; struct _MOF_INFO *
0x140011afc  mov     rcx, rbx; struct _EVENT_RECORD *
0x140011aff  call    ?GetMofCount@@YAPEAU_MOF_COUNT@@PEAU_EVENT_RECORD@@PEAU_MOF_INFO@@PEAU_MOF_VERSION@@@Z; GetMofCount(_EVENT_RECORD *,_MOF_INFO *,_MOF_VERSION *)
0x140011b04  test    rax, rax
0x140011b07  jz      loc_140011C59
0x140011b0d  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140011b14  test    dword ptr [rcx+1910h], 400h
0x140011b1e  jz      short loc_140011B23
0x140011b20  add     [rax+10h], esi
0x140011b23  test    byte ptr [rcx+1910h], 8
0x140011b2a  jz      short loc_140011B33
0x140011b2c  test    ebp, ebp
0x140011b2e  jnz     short loc_140011B33
0x140011b30  add     [rax+14h], esi
0x140011b33  mov     eax, [rcx+1910h]
0x140011b39  test    al, al
0x140011b3b  jns     loc_140011C59
0x140011b41  mov     ebp, 12000000h
0x140011b46  test    ebp, eax
0x140011b48  jnz     short loc_140011B53
0x140011b4a  mov     rdi, [rcx+18F8h]
0x140011b51  jmp     short loc_140011B6B
0x140011b53  call    OpenTempFile
0x140011b58  mov     rdi, rax
0x140011b5b  test    rax, rax
0x140011b5e  jz      loc_140011C59
0x140011b64  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140011b6b  mov     eax, [rcx+1910h]
0x140011b71  test    eax, 3000000h
0x140011b76  jnz     short loc_140011B89
0x140011b78  bt      eax, 1Bh
0x140011b7c  jb      short loc_140011B89
0x140011b7e  bt      eax, 1Ch
0x140011b82  jb      short loc_140011B89
0x140011b84  xor     sil, sil
0x140011b87  jmp     short loc_140011B95
0x140011b89  bt      eax, 1Bh
0x140011b8d  jb      short loc_140011BAA
0x140011b8f  bt      eax, 1Ch
0x140011b93  jb      short loc_140011BAA
0x140011b95  xor     r8d, r8d
0x140011b98  test    sil, sil
0x140011b9b  jnz     short loc_140011BAD
0x140011b9d  mov     rdx, rbx; struct _EVENT_RECORD *
0x140011ba0  mov     rcx, rdi; struct _iobuf *
0x140011ba3  call    ?DumpEventIntoCSV@@YAKPEAU_iobuf@@PEAU_EVENT_RECORD@@@Z; DumpEventIntoCSV(_iobuf *,_EVENT_RECORD *)
0x140011ba8  jmp     short loc_140011BB8
0x140011baa  mov     r8d, esi; int
0x140011bad  mov     rdx, rbx; Event
0x140011bb0  mov     rcx, rdi; struct _iobuf *
0x140011bb3  call    ?DumpEventIntoXML@@YAKPEAU_iobuf@@PEAU_EVENT_RECORD@@H@Z; DumpEventIntoXML(_iobuf *,_EVENT_RECORD *,int)
0x140011bb8  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140011bbf  test    [rax+1910h], ebp
0x140011bc5  jz      loc_140011C59
0x140011bcb  mov     rdx, rdi; struct _iobuf *
0x140011bce  xor     ecx, ecx; unsigned __int8
0x140011bd0  call    ?TracerptFPutc@@YAKEPEAU_iobuf@@@Z; TracerptFPutc(uchar,_iobuf *)
0x140011bd5  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140011bdc  lea     rdx, [rsp+38h+arg_0]
0x140011be1  mov     rcx, rdi
0x140011be4  mov     [rsp+38h+arg_10], 0
0x140011bec  mov     [rsp+38h+arg_0], 0
0x140011bf4  mov     rbp, [rax+2200h]
0x140011bfb  call    ReadTempFile
0x140011c00  mov     rsi, rax
0x140011c03  test    rax, rax
0x140011c06  jz      short loc_140011C4B
0x140011c08  lea     r8, [rsp+38h+arg_10]
0x140011c0d  mov     rdx, rax
0x140011c10  call    ConvertMultiByteToWideChar
0x140011c15  cmp     dword ptr [rdi+1000Ch], 0
0x140011c1c  mov     rbx, rax
0x140011c1f  jz      short loc_140011C35
0x140011c21  call    cs:__imp_GetProcessHeap
0x140011c27  mov     r8, rsi; lpMem
0x140011c2a  xor     edx, edx; dwFlags
0x140011c2c  mov     rcx, rax; hHeap
0x140011c2f  call    cs:__imp_HeapFree
0x140011c35  test    rbx, rbx
0x140011c38  jz      short loc_140011C4B
0x140011c3a  xor     r8d, r8d
0x140011c3d  mov     rdx, rbx
0x140011c40  mov     rcx, rbp
0x140011c43  call    cs:__imp_EvtIntWriteXmlEventToLocalLogfile
0x140011c49  jmp     short loc_140011C51
0x140011c4b  call    cs:__imp_GetLastError
0x140011c51  mov     rcx, rdi; struct _iobuf *
0x140011c54  call    ?TracerptFClose@@YAHPEAU_iobuf@@@Z; TracerptFClose(_iobuf *)
0x140011c59  mov     rbx, [rsp+38h+arg_8]
0x140011c5e  mov     rbp, [rsp+38h+arg_18]
0x140011c63  add     rsp, 20h
0x140011c67  pop     r14
0x140011c69  pop     rdi
0x140011c6a  pop     rsi
0x140011c6b  retn
```
