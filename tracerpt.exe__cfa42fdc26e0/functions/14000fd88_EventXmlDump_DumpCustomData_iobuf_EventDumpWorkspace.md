# EventXmlDump::DumpCustomData(_iobuf *,EventDumpWorkspace *)

- ea: `0x14000fd88`
- end: `0x14000ffc6`
- name: `?DumpCustomData@EventXmlDump@@QEAAKPEAU_iobuf@@PEAVEventDumpWorkspace@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(EventXmlDump *this, struct _iobuf *, struct EventDumpWorkspace *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000faa4`

## callees

- `0x14000f104`
- `0x14000fd88`
- `0x14001601c`
- `0x1400161b0`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fde1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fe7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fde1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fe7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000fdfa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000fe89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000fdfa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000fe89`
- `wevtapi!EvtIntRenderResourceEventTemplate` at `0x14000fe66`
- `wevtapi!EvtIntRenderResourceEventTemplate` at `0x14000fee2`
- `wevtapi!EvtIntRenderResourceEventTemplate` at `0x14000fe66`
- `wevtapi!EvtIntRenderResourceEventTemplate` at `0x14000fee2`

## pseudocode

```c
__int64 __fastcall EventXmlDump::DumpCustomData(EventXmlDump *this, struct _iobuf *a2, struct EventDumpWorkspace *a3)
{
  _BYTE *v5; // rsi
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  struct _EVT_VARIANT *v8; // rax
  EventXmlDump *v9; // rcx
  struct _EVT_VARIANT *v10; // rdi
  unsigned int v12; // ebx
  unsigned int *v13; // rax
  char *v14; // rcx
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  _WORD *v17; // rax
  unsigned int *v18; // rax
  char *v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // ebp
  unsigned int v22; // r12d
  wchar_t *UInt16Arr; // r14
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  _DWORD v27[4]; // [rsp+40h] [rbp-848h] BYREF
  _BYTE Mem[2048]; // [rsp+50h] [rbp-838h] BYREF

  v5 = Mem;
  TracerptFPuts("\t<UserData>\r\n", a2);
  v6 = *(_DWORD *)(*((_QWORD *)a3 + 1) + 104LL);
  if ( !v6 )
  {
    v12 = 0;
    v10 = 0;
    goto LABEL_18;
  }
  v27[0] = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (struct _EVT_VARIANT *)HeapAlloc(ProcessHeap, 8u, 16LL * v6);
  v10 = v8;
  if ( !v8 )
    return 8;
  v12 = EventXmlDump::ConvertIntoEvtArray(v9, a3, v8);
  if ( !v12 )
  {
    v13 = (unsigned int *)*((_QWORD *)a3 + 1);
    if ( v13[21] )
      v14 = (char *)v13 + v13[21];
    else
      v14 = 0;
    v12 = EvtIntRenderResourceEventTemplate(v14, v13[22], v10, v13[26], 0, 1024, Mem, v27);
    if ( v12 == 122 )
    {
      v15 = 2LL * v27[0];
      v16 = GetProcessHeap();
      v17 = HeapAlloc(v16, 8u, v15);
      v5 = v17;
      if ( !v17 )
      {
        v12 = 8;
LABEL_20:
        v20 = *((_QWORD *)a3 + 1);
        v21 = 0;
        v22 = *(_DWORD *)(v20 + 104);
        if ( v22 )
        {
          do
          {
            UInt16Arr = v10[v21].UInt16Arr;
            if ( UInt16Arr && UInt16Arr != &Ext )
            {
              v24 = GetProcessHeap();
              HeapFree(v24, 0, UInt16Arr);
            }
            ++v21;
          }
          while ( v21 < v22 );
        }
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v10);
        goto LABEL_26;
      }
      *v17 = 0;
      v18 = (unsigned int *)*((_QWORD *)a3 + 1);
      if ( v18[21] )
        v19 = (char *)v18 + v18[21];
      else
        v19 = 0;
      v12 = EvtIntRenderResourceEventTemplate(v19, v18[22], v10, v18[26], 0, v27[0], v5, v27);
    }
    if ( !v12 )
    {
      TracerptFPrintf(a2, "\t\t%ws", v5);
LABEL_18:
      TracerptFPuts("\r\n\t</UserData>\r\n", a2);
    }
  }
  if ( v10 )
    goto LABEL_20;
LABEL_26:
  if ( v5 != Mem )
  {
    if ( v5 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v5);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x14000fd88  mov     [rsp+arg_0], rbx
0x14000fd8d  mov     [rsp+arg_18], rbp
0x14000fd92  push    rsi
0x14000fd93  push    rdi
0x14000fd94  push    r12
0x14000fd96  push    r14
0x14000fd98  push    r15
0x14000fd9a  sub     rsp, 860h
0x14000fda1  mov     rax, cs:__security_cookie
0x14000fda8  xor     rax, rsp
0x14000fdab  mov     [rsp+888h+var_38], rax
0x14000fdb3  lea     rcx, aUserdata_1; "\t<UserData>\r\n"
0x14000fdba  mov     rbp, r8
0x14000fdbd  mov     r14, rdx
0x14000fdc0  lea     rsi, [rsp+888h+Mem]
0x14000fdc5  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000fdca  mov     rax, [rbp+8]
0x14000fdce  mov     ebx, [rax+68h]
0x14000fdd1  test    ebx, ebx
0x14000fdd3  jz      loc_14000FF02
0x14000fdd9  mov     [rsp+888h+var_848], 0
0x14000fde1  call    cs:__imp_GetProcessHeap
0x14000fde7  mov     r8d, ebx
0x14000fdea  mov     r15d, 8
0x14000fdf0  shl     r8, 4; dwBytes
0x14000fdf4  mov     edx, r15d; dwFlags
0x14000fdf7  mov     rcx, rax; hHeap
0x14000fdfa  call    cs:__imp_HeapAlloc
0x14000fe00  mov     rdi, rax
0x14000fe03  test    rax, rax
0x14000fe06  jnz     short loc_14000FE10
0x14000fe08  mov     eax, r15d
0x14000fe0b  jmp     loc_14000FF9A
0x14000fe10  mov     r8, rdi; struct _EVT_VARIANT *
0x14000fe13  mov     rdx, rbp; struct EventDumpWorkspace *
0x14000fe16  call    ?ConvertIntoEvtArray@EventXmlDump@@QEAAKPEAVEventDumpWorkspace@@PEAU_EVT_VARIANT@@@Z; EventXmlDump::ConvertIntoEvtArray(EventDumpWorkspace *,_EVT_VARIANT *)
0x14000fe1b  mov     ebx, eax
0x14000fe1d  test    eax, eax
0x14000fe1f  jnz     loc_14000FF15
0x14000fe25  mov     rax, [rbp+8]
0x14000fe29  mov     r9d, [rax+68h]
0x14000fe2d  mov     edx, [rax+58h]
0x14000fe30  cmp     [rax+54h], ebx
0x14000fe33  jnz     short loc_14000FE39
0x14000fe35  xor     ecx, ecx
0x14000fe37  jmp     short loc_14000FE3F
0x14000fe39  mov     ecx, [rax+54h]
0x14000fe3c  add     rcx, rax
0x14000fe3f  lea     rax, [rsp+888h+var_848]
0x14000fe44  mov     r8, rdi
0x14000fe47  mov     [rsp+888h+var_850], rax
0x14000fe4c  lea     rax, [rsp+888h+Mem]
0x14000fe51  mov     [rsp+888h+var_858], rax
0x14000fe56  mov     [rsp+888h+var_860], 400h
0x14000fe5e  mov     [rsp+888h+var_868], 0
0x14000fe66  call    cs:__imp_EvtIntRenderResourceEventTemplate
0x14000fe6c  mov     ebx, eax
0x14000fe6e  cmp     eax, 7Ah ; 'z'
0x14000fe71  jnz     short loc_14000FEEA
0x14000fe73  mov     ebx, [rsp+888h+var_848]
0x14000fe77  add     rbx, rbx
0x14000fe7a  call    cs:__imp_GetProcessHeap
0x14000fe80  mov     r8, rbx; dwBytes
0x14000fe83  mov     edx, r15d; dwFlags
0x14000fe86  mov     rcx, rax; hHeap
0x14000fe89  call    cs:__imp_HeapAlloc
0x14000fe8f  mov     rsi, rax
0x14000fe92  test    rax, rax
0x14000fe95  jnz     short loc_14000FE9C
0x14000fe97  mov     ebx, r15d
0x14000fe9a  jmp     short loc_14000FF1A
0x14000fe9c  xor     eax, eax
0x14000fe9e  mov     [rsi], ax
0x14000fea1  mov     rax, [rbp+8]
0x14000fea5  mov     edx, [rsp+888h+var_848]
0x14000fea9  cmp     dword ptr [rax+54h], 0
0x14000fead  mov     r9d, [rax+68h]
0x14000feb1  mov     r10d, [rax+58h]
0x14000feb5  jnz     short loc_14000FEBB
0x14000feb7  xor     ecx, ecx
0x14000feb9  jmp     short loc_14000FEC1
0x14000febb  mov     ecx, [rax+54h]
0x14000febe  add     rcx, rax
0x14000fec1  lea     rax, [rsp+888h+var_848]
0x14000fec6  mov     r8, rdi
0x14000fec9  mov     [rsp+888h+var_850], rax
0x14000fece  mov     [rsp+888h+var_858], rsi
0x14000fed3  mov     [rsp+888h+var_860], edx
0x14000fed7  mov     edx, r10d
0x14000feda  mov     [rsp+888h+var_868], 0
0x14000fee2  call    cs:__imp_EvtIntRenderResourceEventTemplate
0x14000fee8  mov     ebx, eax
0x14000feea  test    ebx, ebx
0x14000feec  jnz     short loc_14000FF15
0x14000feee  mov     r8, rsi
0x14000fef1  lea     rdx, aWs; "\t\t%ws"
0x14000fef8  mov     rcx, r14; struct _iobuf *
0x14000fefb  call    ?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ; TracerptFPrintf(_iobuf *,char const *,...)
0x14000ff00  jmp     short loc_14000FF06
0x14000ff02  xor     ebx, ebx
0x14000ff04  xor     edi, edi
0x14000ff06  mov     rdx, r14; struct _iobuf *
0x14000ff09  lea     rcx, aUserdata_2; "\r\n\t</UserData>\r\n"
0x14000ff10  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14000ff15  test    rdi, rdi
0x14000ff18  jz      short loc_14000FF75
0x14000ff1a  mov     rax, [rbp+8]
0x14000ff1e  mov     r15, rdi
0x14000ff21  xor     ebp, ebp
0x14000ff23  mov     r12d, [rax+68h]
0x14000ff27  test    r12d, r12d
0x14000ff2a  jz      short loc_14000FF61
0x14000ff2c  mov     eax, ebp
0x14000ff2e  add     rax, rax
0x14000ff31  mov     r14, [r15+rax*8]
0x14000ff35  test    r14, r14
0x14000ff38  jz      short loc_14000FF5A
0x14000ff3a  lea     rax, Ext
0x14000ff41  cmp     r14, rax
0x14000ff44  jz      short loc_14000FF5A
0x14000ff46  call    cs:__imp_GetProcessHeap
0x14000ff4c  mov     r8, r14; lpMem
0x14000ff4f  xor     edx, edx; dwFlags
0x14000ff51  mov     rcx, rax; hHeap
0x14000ff54  call    cs:__imp_HeapFree
0x14000ff5a  inc     ebp
0x14000ff5c  cmp     ebp, r12d
0x14000ff5f  jb      short loc_14000FF2C
0x14000ff61  call    cs:__imp_GetProcessHeap
0x14000ff67  mov     r8, rdi; lpMem
0x14000ff6a  xor     edx, edx; dwFlags
0x14000ff6c  mov     rcx, rax; hHeap
0x14000ff6f  call    cs:__imp_HeapFree
0x14000ff75  lea     rax, [rsp+888h+Mem]
0x14000ff7a  cmp     rsi, rax
0x14000ff7d  jz      short loc_14000FF98
0x14000ff7f  test    rsi, rsi
0x14000ff82  jz      short loc_14000FF98
0x14000ff84  call    cs:__imp_GetProcessHeap
0x14000ff8a  mov     r8, rsi; lpMem
0x14000ff8d  xor     edx, edx; dwFlags
0x14000ff8f  mov     rcx, rax; hHeap
0x14000ff92  call    cs:__imp_HeapFree
0x14000ff98  mov     eax, ebx
0x14000ff9a  mov     rcx, [rsp+888h+var_38]
0x14000ffa2  xor     rcx, rsp; StackCookie
0x14000ffa5  call    __security_check_cookie
0x14000ffaa  lea     r11, [rsp+888h+var_28]
0x14000ffb2  mov     rbx, [r11+30h]
0x14000ffb6  mov     rbp, [r11+48h]
0x14000ffba  mov     rsp, r11
0x14000ffbd  pop     r15
0x14000ffbf  pop     r14
0x14000ffc1  pop     r12
0x14000ffc3  pop     rdi
0x14000ffc4  pop     rsi
0x14000ffc5  retn
```
