# CNotification::Update(IXMLDOMNode *)

- ea: `0x1800040b4`
- end: `0x180004251`
- name: `?Update@CNotification@@QEAAJPEAUIXMLDOMNode@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180006770`

## callees

- `0x180003e10`
- `0x1800040b4`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b498`
- `0x18000b884`
- `0x18000d010`

## string_xrefs

- `0x1800041bf`: `CNotification::SchdpUpdateParameters`
- `0x1800041e9`: `CNotification::SchdpUpdateParameters`
- `0x180004227`: `CNotification::Update`

## pseudocode

```c
__int64 __fastcall CNotification::Update(struct IXMLDOMDocument2 *this, struct IXMLDOMNode *a2)
{
  int v2; // ebx
  struct IXMLDOMNode *v3; // rdi
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v6; // r14
  int v7; // r9d
  int v8; // r8d
  int v9; // esi
  int v10; // eax
  int v11; // eax
  int updated; // eax
  int v14; // [rsp+50h] [rbp+8h] BYREF
  struct IXMLDOMNode *v15; // [rsp+60h] [rbp+18h] BYREF
  struct IXMLDOMNodeList *v16; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v3 = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  if ( !this[3].lpVtbl )
    return (unsigned int)v2;
  ChildNodes = SdpXmlGetChildNodes(this, a2, &v16, (unsigned int *)&v14);
  v6 = v16;
  v2 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    if ( (unsigned int)v14 <= 0x7FFFFFFF )
    {
      v2 = 0;
      v9 = 0;
      if ( v14 > 0 )
      {
        while ( 1 )
        {
          if ( v3 )
          {
            ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
            v15 = 0;
          }
          v10 = SdpXmlNextNode(v6, &v15);
          v2 = v10;
          if ( v10 < 0 )
            break;
          v3 = v15;
          v11 = SdpXmlCheckNode(v15, L"Parameter");
          v2 = v11;
          if ( v11 < 0 )
          {
            v7 = v11;
            v8 = 521;
            goto LABEL_21;
          }
          if ( v11 == 1 || !v3 )
          {
            v2 = -2147467259;
            v8 = 521;
            goto LABEL_20;
          }
          updated = CNotification::SchdpUpdateParameter((CNotification *)this, v3, v9);
          v2 = updated;
          if ( updated < 0 )
          {
            v7 = updated;
            v8 = 524;
            goto LABEL_21;
          }
          if ( ++v9 >= v14 )
            goto LABEL_22;
        }
        SdpDebugTrace(1u, L"CNotification::SchdpUpdateParameters", 520, v10);
        v3 = v15;
      }
      goto LABEL_22;
    }
    v2 = -2147024362;
    v8 = 513;
LABEL_20:
    v7 = v2;
  }
  else
  {
    v7 = ChildNodes;
    v8 = 509;
  }
LABEL_21:
  SdpDebugTrace(1u, L"CNotification::SchdpUpdateParameters", v8, v7);
LABEL_22:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  if ( v2 < 0 )
    SdpDebugTrace(1u, L"CNotification::Update", 929, v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800040b4  mov     rax, rsp
0x1800040b7  mov     [rax+10h], rbx
0x1800040bb  push    rsi
0x1800040bc  push    rdi
0x1800040bd  push    r13
0x1800040bf  push    r14
0x1800040c1  push    r15
0x1800040c3  sub     rsp, 20h
0x1800040c7  xor     ebx, ebx
0x1800040c9  xor     edi, edi
0x1800040cb  and     [rax+8], ebx
0x1800040ce  mov     r15, rcx
0x1800040d1  and     [rax+20h], rbx
0x1800040d5  mov     [rax+18h], rdi
0x1800040d9  cmp     [rcx+18h], rbx
0x1800040dd  jz      loc_18000423C
0x1800040e3  lea     r9, [rax+8]; unsigned int *
0x1800040e7  lea     r8, [rax+20h]; struct IXMLDOMNodeList **
0x1800040eb  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x1800040f0  mov     r14, [rsp+48h+arg_18]
0x1800040f5  mov     ebx, eax
0x1800040f7  lea     r13d, [rdi+1]
0x1800040fb  test    eax, eax
0x1800040fd  jns     short loc_18000410D
0x1800040ff  mov     r9d, eax
0x180004102  mov     r8d, 1FDh
0x180004108  jmp     loc_1800041E9
0x18000410d  cmp     [rsp+48h+arg_0], 7FFFFFFFh
0x180004115  ja      loc_1800041DB
0x18000411b  xor     ebx, ebx
0x18000411d  xor     esi, esi
0x18000411f  cmp     [rsp+48h+arg_0], ebx
0x180004123  jle     loc_1800041F8
0x180004129  test    rdi, rdi
0x18000412c  jz      short loc_180004143
0x18000412e  mov     rax, [rdi]
0x180004131  mov     rcx, rdi
0x180004134  mov     rax, [rax+10h]
0x180004138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413d  and     [rsp+48h+arg_10], 0
0x180004143  lea     rdx, [rsp+48h+arg_10]; struct IXMLDOMNode **
0x180004148  mov     rcx, r14; struct IXMLDOMNodeList *
0x18000414b  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180004150  mov     ebx, eax
0x180004152  test    eax, eax
0x180004154  js      short loc_1800041BC
0x180004156  mov     rdi, [rsp+48h+arg_10]
0x18000415b  lea     rdx, aParameter; "Parameter"
0x180004162  mov     rcx, rdi; struct IXMLDOMNode *
0x180004165  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18000416a  mov     ebx, eax
0x18000416c  test    eax, eax
0x18000416e  js      short loc_1800041B1
0x180004170  cmp     eax, r13d
0x180004173  jz      short loc_1800041A4
0x180004175  test    rdi, rdi
0x180004178  jz      short loc_1800041A4
0x18000417a  mov     r8d, esi; int
0x18000417d  mov     rdx, rdi; struct IXMLDOMNode *
0x180004180  mov     rcx, r15; this
0x180004183  call    ?SchdpUpdateParameter@CNotification@@AEAAJPEAUIXMLDOMNode@@J@Z; CNotification::SchdpUpdateParameter(IXMLDOMNode *,long)
0x180004188  mov     ebx, eax
0x18000418a  test    eax, eax
0x18000418c  js      short loc_180004199
0x18000418e  add     esi, r13d
0x180004191  cmp     esi, [rsp+48h+arg_0]
0x180004195  jl      short loc_180004129
0x180004197  jmp     short loc_1800041F8
0x180004199  mov     r9d, eax
0x18000419c  mov     r8d, 20Ch
0x1800041a2  jmp     short loc_1800041E9
0x1800041a4  mov     ebx, 80004005h
0x1800041a9  mov     r8d, 209h
0x1800041af  jmp     short loc_1800041E6
0x1800041b1  mov     r9d, eax
0x1800041b4  mov     r8d, 209h
0x1800041ba  jmp     short loc_1800041E9
0x1800041bc  mov     r9d, eax; int
0x1800041bf  lea     rdx, aCnotificationS_4; "CNotification::SchdpUpdateParameters"
0x1800041c6  mov     r8d, 208h; int
0x1800041cc  mov     ecx, r13d; Level
0x1800041cf  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800041d4  mov     rdi, [rsp+48h+arg_10]
0x1800041d9  jmp     short loc_1800041F8
0x1800041db  mov     ebx, 80070216h
0x1800041e0  mov     r8d, 201h; int
0x1800041e6  mov     r9d, ebx; int
0x1800041e9  lea     rdx, aCnotificationS_4; "CNotification::SchdpUpdateParameters"
0x1800041f0  mov     ecx, r13d; Level
0x1800041f3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800041f8  test    r14, r14
0x1800041fb  jz      short loc_18000420C
0x1800041fd  mov     rax, [r14]
0x180004200  mov     rcx, r14
0x180004203  mov     rax, [rax+10h]
0x180004207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420c  test    rdi, rdi
0x18000420f  jz      short loc_180004220
0x180004211  mov     rax, [rdi]
0x180004214  mov     rcx, rdi
0x180004217  mov     rax, [rax+10h]
0x18000421b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004220  test    ebx, ebx
0x180004222  jns     short loc_18000423C
0x180004224  mov     r9d, ebx; int
0x180004227  lea     rdx, aCnotificationU; "CNotification::Update"
0x18000422e  mov     r8d, 3A1h; int
0x180004234  mov     ecx, r13d; Level
0x180004237  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000423c  mov     eax, ebx
0x18000423e  mov     rbx, [rsp+48h+arg_8]
0x180004243  add     rsp, 20h
0x180004247  pop     r15
0x180004249  pop     r14
0x18000424b  pop     r13
0x18000424d  pop     rdi
0x18000424e  pop     rsi
0x18000424f  retn
```
