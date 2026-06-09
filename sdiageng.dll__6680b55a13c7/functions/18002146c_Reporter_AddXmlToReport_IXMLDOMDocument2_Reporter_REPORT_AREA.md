# Reporter::AddXmlToReport(IXMLDOMDocument2 *,Reporter::_REPORT_AREA)

- ea: `0x18002146c`
- end: `0x1800215dd`
- name: `?AddXmlToReport@Reporter@@QEAAJPEAUIXMLDOMDocument2@@W4_REPORT_AREA@1@@Z`
- size: `369`
- prototype: `__int64 __fastcall(__int64, struct IXMLDOMDocument2 *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004518`
- `0x180015730`
- `0x180016630`
- `0x180017438`
- `0x18001e194`

## callees

- `0x18002146c`
- `0x180026fa0`
- `0x180027ea4`
- `0x18002a010`

## string_xrefs

- `0x180021583`: `Reporter::AddXmlToReport`

## pseudocode

```c
__int64 __fastcall Reporter::AddXmlToReport(__int64 a1, struct IXMLDOMDocument2 *a2, int a3)
{
  unsigned int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebp
  __int64 v10; // r14
  struct IXMLDOMElement *v11; // r14
  int v12; // eax
  unsigned int v13; // ebp
  __int64 v14; // rax
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF
  __int64 v17; // [rsp+68h] [rbp+20h] BYREF

  v16 = 0;
  v17 = 0;
  if ( a2 )
  {
    v6 = 0;
    v9 = 0;
    if ( *(_DWORD *)(a1 + 40) )
    {
      while ( 1 )
      {
        v10 = *(_QWORD *)(a1 + 32);
        if ( a3 == *(_DWORD *)(v10 + 16LL * v9) )
        {
          v11 = *(struct IXMLDOMElement **)(v10 + 16LL * v9 + 8);
          if ( a3 == 3 )
          {
            v12 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))v11->lpVtbl->get_firstChild)(v11, &v16);
            v6 = v12;
            if ( v12 < 0 )
            {
              v7 = 281;
              goto LABEL_20;
            }
            if ( v12 != 1 )
            {
              v12 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, __int64 *))v11->lpVtbl->removeChild)(
                      v11,
                      v16,
                      &v17);
              v6 = v12;
              if ( v12 < 0 )
              {
                v7 = 285;
                goto LABEL_20;
              }
            }
          }
          v12 = SdpXmlAppend(0, v11, a2);
          v6 = v12;
          if ( v12 < 0 )
            break;
        }
        if ( ++v9 >= *(_DWORD *)(a1 + 40) )
          goto LABEL_11;
      }
      v7 = 290;
    }
    else
    {
LABEL_11:
      v13 = 0;
      if ( !*(_DWORD *)(a1 + 16) )
        goto LABEL_22;
      while ( 1 )
      {
        v14 = *(_QWORD *)(a1 + 8);
        if ( a3 == *(_DWORD *)(v14 + 16LL * v13) )
        {
          v12 = SdpXmlAppend(0, *(struct IXMLDOMElement **)(v14 + 16LL * v13 + 8), a2);
          v6 = v12;
          if ( v12 < 0 )
            break;
        }
        if ( ++v13 >= *(_DWORD *)(a1 + 16) )
          goto LABEL_22;
      }
      v7 = 300;
    }
LABEL_20:
    v8 = v12;
  }
  else
  {
    v6 = -2147024809;
    v7 = 268;
    v8 = -2147024809;
  }
  SdpDebugTrace(1u, L"Reporter::AddXmlToReport", v7, v8);
LABEL_22:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return v6;
}

```

## disassembly

```asm
0x18002146c  mov     [rsp+arg_0], rbx
0x180021471  push    rbp
0x180021472  push    rsi
0x180021473  push    r12
0x180021475  push    r14
0x180021477  push    r15
0x180021479  sub     rsp, 20h
0x18002147d  mov     [rsp+48h+arg_8], 0
0x180021486  mov     r15d, r8d
0x180021489  mov     [rsp+48h+arg_18], 0
0x180021492  mov     r12, rdx
0x180021495  mov     rsi, rcx
0x180021498  test    rdx, rdx
0x18002149b  jnz     short loc_1800214B0
0x18002149d  mov     ebx, 80070057h
0x1800214a2  mov     r8d, 10Ch
0x1800214a8  mov     r9d, ebx
0x1800214ab  jmp     loc_180021583
0x1800214b0  xor     ebx, ebx
0x1800214b2  xor     ebp, ebp
0x1800214b4  cmp     [rcx+28h], ebx
0x1800214b7  jbe     short loc_18002152E
0x1800214b9  mov     r14, [rsi+20h]
0x1800214bd  mov     eax, ebp
0x1800214bf  add     rax, rax
0x1800214c2  cmp     r15d, [r14+rax*8]
0x1800214c6  jnz     short loc_180021527
0x1800214c8  mov     r14, [r14+rax*8+8]
0x1800214cd  cmp     r15d, 3
0x1800214d1  jnz     short loc_180021514
0x1800214d3  mov     rax, [r14]
0x1800214d6  lea     rdx, [rsp+48h+arg_8]
0x1800214db  mov     rcx, r14
0x1800214de  mov     rax, [rax+68h]
0x1800214e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214e7  mov     ebx, eax
0x1800214e9  test    eax, eax
0x1800214eb  js      short loc_18002156A
0x1800214ed  cmp     eax, 1
0x1800214f0  jz      short loc_180021514
0x1800214f2  mov     rax, [r14]
0x1800214f5  lea     r8, [rsp+48h+arg_18]
0x1800214fa  mov     rdx, [rsp+48h+arg_8]
0x1800214ff  mov     rcx, r14
0x180021502  mov     rax, [rax+0A0h]
0x180021509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002150e  mov     ebx, eax
0x180021510  test    eax, eax
0x180021512  js      short loc_180021562
0x180021514  mov     r8, r12; struct IXMLDOMDocument2 *
0x180021517  mov     rdx, r14; struct IXMLDOMElement *
0x18002151a  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18002151c  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180021521  mov     ebx, eax
0x180021523  test    eax, eax
0x180021525  js      short loc_180021572
0x180021527  inc     ebp
0x180021529  cmp     ebp, [rsi+28h]
0x18002152c  jb      short loc_1800214B9
0x18002152e  xor     ebp, ebp
0x180021530  cmp     [rsi+10h], ebp
0x180021533  jbe     short loc_180021594
0x180021535  mov     rax, [rsi+8]
0x180021539  mov     edx, ebp
0x18002153b  add     rdx, rdx
0x18002153e  cmp     r15d, [rax+rdx*8]
0x180021542  jnz     short loc_180021559
0x180021544  mov     rdx, [rax+rdx*8+8]; struct IXMLDOMElement *
0x180021549  mov     r8, r12; struct IXMLDOMDocument2 *
0x18002154c  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18002154e  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180021553  mov     ebx, eax
0x180021555  test    eax, eax
0x180021557  js      short loc_18002157A
0x180021559  inc     ebp
0x18002155b  cmp     ebp, [rsi+10h]
0x18002155e  jb      short loc_180021535
0x180021560  jmp     short loc_180021594
0x180021562  mov     r8d, 11Dh
0x180021568  jmp     short loc_180021580
0x18002156a  mov     r8d, 119h
0x180021570  jmp     short loc_180021580
0x180021572  mov     r8d, 122h
0x180021578  jmp     short loc_180021580
0x18002157a  mov     r8d, 12Ch; int
0x180021580  mov     r9d, eax; int
0x180021583  lea     rdx, aReporterAddxml; "Reporter::AddXmlToReport"
0x18002158a  mov     ecx, 1; Level
0x18002158f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021594  mov     rcx, [rsp+48h+arg_8]
0x180021599  test    rcx, rcx
0x18002159c  jz      short loc_1800215B3
0x18002159e  mov     rax, [rcx]
0x1800215a1  mov     rax, [rax+10h]
0x1800215a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215aa  mov     [rsp+48h+arg_8], 0
0x1800215b3  mov     rcx, [rsp+48h+arg_18]
0x1800215b8  test    rcx, rcx
0x1800215bb  jz      short loc_1800215C9
0x1800215bd  mov     rax, [rcx]
0x1800215c0  mov     rax, [rax+10h]
0x1800215c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215c9  mov     eax, ebx
0x1800215cb  mov     rbx, [rsp+48h+arg_0]
0x1800215d0  add     rsp, 20h
0x1800215d4  pop     r15
0x1800215d6  pop     r14
0x1800215d8  pop     r12
0x1800215da  pop     rsi
0x1800215db  pop     rbp
0x1800215dc  retn
```
