# CTpTransport::BuildRequestXML(CTpRequestMessage *,ITpCallbacks *,CMemoryByteStream &,long &,ulong &)

- ea: `0x1800221e4`
- end: `0x18002253a`
- name: `?BuildRequestXML@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUITpCallbacks@@AEAVCMemoryByteStream@@AEAJAEAK@Z`
- size: `854`
- prototype: `__int64 __usercall@<rax>(struct CTpRequestMessage *this@<rcx>, struct ITpCallbacks *@<rdx>, struct CMemoryByteStream *@<r8>, int *@<r9>, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e2b4`
- `0x180086a60`
- `0x18008ab10`

## callees

- `0x180020680`
- `0x1800221e4`
- `0x180022540`
- `0x18003de9c`
- `0x1800490c0`
- `0x18004e744`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002221c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022431`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002221c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022431`
- `XmlLite!CreateXmlWriter` at `0x180022257`
- `XmlLite!CreateXmlWriter` at `0x180022257`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CTpTransport::BuildRequestXML(
        struct CTpRequestMessage *this,
        struct ITpCallbacks *a2,
        struct CMemoryByteStream *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  CMemoryByteStream *v8; // r8
  DWORD TickCount; // r15d
  HRESULT v10; // eax
  __int64 v11; // r8
  unsigned int v12; // ebx
  wchar_t **v13; // rdx
  wchar_t *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  void *v17; // rcx
  void *v18; // rcx
  void *ppvObject; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v21[2]; // [rsp+28h] [rbp-18h] BYREF
  int v22; // [rsp+38h] [rbp-8h]

  CIStreamAdapter::CIStreamAdapter((CIStreamAdapter *)v21, a3);
  CMemoryByteStream::OpenForReadWrite(v8);
  TickCount = GetTickCount();
  ppvObject = 0;
  v10 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v12 = v10;
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2, 1);
    v12 = v10;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
      v12 = v10;
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 2);
        v12 = v10;
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(void *, _QWORD *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v21);
          v12 = v10;
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 208LL))(ppvObject, 1);
            v12 = v10;
            if ( v10 >= 0 )
            {
              if ( a2 )
                (*(void (__fastcall **)(struct ITpCallbacks *))(*(_QWORD *)a2 + 8LL))(a2);
              v12 = CTpRequestMessage::Write(this, (struct IXmlWriter *)ppvObject);
              *a5 = GetTickCount() - TickCount;
              *a4 = v12;
              if ( (v12 & 0x80000000) == 0 )
              {
                v10 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                v12 = v10;
                if ( v10 >= 0 )
                {
                  v17 = ppvObject;
                  ppvObject = 0;
                  if ( v17 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
                  if ( a2 )
                    (*(void (__fastcall **)(struct ITpCallbacks *))(*(_QWORD *)a2 + 24LL))(a2);
                }
                else
                {
                  v13 = &WPP_GLOBAL_Control;
                  v14 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v15 = 37;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                if ( a2 )
                  (*(void (__fastcall **)(struct ITpCallbacks *, _QWORD))(*(_QWORD *)a2 + 16LL))(a2, v12);
                v13 = &WPP_GLOBAL_Control;
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v15 = 36;
                  v16 = v12;
                  goto LABEL_6;
                }
              }
            }
            else
            {
              v13 = &WPP_GLOBAL_Control;
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v15 = 35;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v13 = &WPP_GLOBAL_Control;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v15 = 34;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v13 = &WPP_GLOBAL_Control;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v15 = 33;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v13 = &WPP_GLOBAL_Control;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v15 = 32;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v13 = &WPP_GLOBAL_Control;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v15 = 31;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v13 = &WPP_GLOBAL_Control;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v15 = 30;
LABEL_5:
      v16 = (unsigned int)v10;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v16);
    }
  }
  v18 = ppvObject;
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  v21[0] = &CIStreamAdapter::`vftable';
  if ( v22 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18, v13, v11);
  return v12;
}

```

## disassembly

```asm
0x1800221e4  push    rbp
0x1800221e6  push    rbx
0x1800221e7  push    rsi
0x1800221e8  push    rdi
0x1800221e9  push    r13
0x1800221eb  push    r14
0x1800221ed  push    r15
0x1800221ef  mov     rbp, rsp
0x1800221f2  sub     rsp, 40h
0x1800221f6  mov     rsi, r9
0x1800221f9  mov     rdi, rdx
0x1800221fc  mov     r14, rcx
0x1800221ff  mov     rdx, r8; struct IWerByteStream *
0x180022202  lea     rcx, [rbp+var_18]; this
0x180022206  call    ??0CIStreamAdapter@@QEAA@PEAUIWerByteStream@@@Z; CIStreamAdapter::CIStreamAdapter(IWerByteStream *)
0x18002220b  nop
0x18002220c  mov     [rbp+ppvObject], 0
0x180022214  mov     rcx, r8; this
0x180022217  call    ?OpenForReadWrite@CMemoryByteStream@@QEAAXXZ; CMemoryByteStream::OpenForReadWrite(void)
0x18002221c  call    cs:__imp_GetTickCount
0x180022223  nop     dword ptr [rax+rax+00h]
0x180022228  mov     r15d, eax
0x18002222b  mov     rcx, [rbp+ppvObject]
0x18002222f  mov     [rbp+ppvObject], 0
0x180022237  test    rcx, rcx
0x18002223a  jz      short loc_180022249
0x18002223c  mov     rdx, [rcx]
0x18002223f  mov     rax, [rdx+10h]
0x180022243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022248  nop
0x180022249  xor     r8d, r8d; pMalloc
0x18002224c  lea     rdx, [rbp+ppvObject]; ppvObject
0x180022250  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180022257  call    cs:__imp_CreateXmlWriter
0x18002225e  nop     dword ptr [rax+rax+00h]
0x180022263  mov     ebx, eax
0x180022265  mov     r13d, 1
0x18002226b  test    eax, eax
0x18002226d  jns     short loc_1800222AC
0x18002226f  lea     rdx, WPP_GLOBAL_Control
0x180022276  mov     rcx, cs:WPP_GLOBAL_Control
0x18002227d  cmp     rcx, rdx
0x180022280  jz      loc_1800224FB
0x180022286  test    [rcx+1Ch], r13b
0x18002228a  jz      loc_1800224FB
0x180022290  lea     edx, [r13+1Dh]
0x180022294  mov     r9d, eax
0x180022297  lea     r8, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids
0x18002229e  mov     rcx, [rcx+10h]
0x1800222a2  call    WPP_SF_d
0x1800222a7  jmp     loc_1800224FB
0x1800222ac  mov     rcx, [rbp+ppvObject]
0x1800222b0  mov     rax, [rcx]
0x1800222b3  mov     r8, r13
0x1800222b6  mov     edx, 2
0x1800222bb  mov     rax, [rax+28h]
0x1800222bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222c4  mov     ebx, eax
0x1800222c6  test    eax, eax
0x1800222c8  jns     short loc_1800222F2
0x1800222ca  lea     rdx, WPP_GLOBAL_Control
0x1800222d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222d8  cmp     rcx, rdx
0x1800222db  jz      loc_1800224FB
0x1800222e1  test    [rcx+1Ch], r13b
0x1800222e5  jz      loc_1800224FB
0x1800222eb  mov     edx, 1Fh
0x1800222f0  jmp     short loc_180022294
0x1800222f2  mov     rcx, [rbp+ppvObject]
0x1800222f6  mov     rax, [rcx]
0x1800222f9  mov     r8, r13
0x1800222fc  mov     edx, r13d
0x1800222ff  mov     rax, [rax+28h]
0x180022303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022308  mov     ebx, eax
0x18002230a  test    eax, eax
0x18002230c  jns     short loc_180022339
0x18002230e  lea     rdx, WPP_GLOBAL_Control
0x180022315  mov     rcx, cs:WPP_GLOBAL_Control
0x18002231c  cmp     rcx, rdx
0x18002231f  jz      loc_1800224FB
0x180022325  test    [rcx+1Ch], r13b
0x180022329  jz      loc_1800224FB
0x18002232f  mov     edx, 20h ; ' '
0x180022334  jmp     loc_180022294
0x180022339  mov     rcx, [rbp+ppvObject]
0x18002233d  mov     rax, [rcx]
0x180022340  mov     edx, 4
0x180022345  lea     r8d, [rdx-2]
0x180022349  mov     rax, [rax+28h]
0x18002234d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022352  mov     ebx, eax
0x180022354  test    eax, eax
0x180022356  jns     short loc_180022383
0x180022358  lea     rdx, WPP_GLOBAL_Control
0x18002235f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022366  cmp     rcx, rdx
0x180022369  jz      loc_1800224FB
0x18002236f  test    [rcx+1Ch], r13b
0x180022373  jz      loc_1800224FB
0x180022379  mov     edx, 21h ; '!'
0x18002237e  jmp     loc_180022294
0x180022383  mov     rcx, [rbp+ppvObject]
0x180022387  mov     rax, [rcx]
0x18002238a  lea     rdx, [rbp+var_18]
0x18002238e  mov     rax, [rax+18h]
0x180022392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022397  mov     ebx, eax
0x180022399  test    eax, eax
0x18002239b  jns     short loc_1800223C8
0x18002239d  lea     rdx, WPP_GLOBAL_Control
0x1800223a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223ab  cmp     rcx, rdx
0x1800223ae  jz      loc_1800224FB
0x1800223b4  test    [rcx+1Ch], r13b
0x1800223b8  jz      loc_1800224FB
0x1800223be  mov     edx, 22h ; '"'
0x1800223c3  jmp     loc_180022294
0x1800223c8  mov     rcx, [rbp+ppvObject]
0x1800223cc  mov     rax, [rcx]
0x1800223cf  mov     edx, r13d
0x1800223d2  mov     rax, [rax+0D0h]
0x1800223d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223de  mov     ebx, eax
0x1800223e0  test    eax, eax
0x1800223e2  jns     short loc_18002240F
0x1800223e4  lea     rdx, WPP_GLOBAL_Control
0x1800223eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223f2  cmp     rcx, rdx
0x1800223f5  jz      loc_1800224FB
0x1800223fb  test    [rcx+1Ch], r13b
0x1800223ff  jz      loc_1800224FB
0x180022405  mov     edx, 23h ; '#'
0x18002240a  jmp     loc_180022294
0x18002240f  test    rdi, rdi
0x180022412  jz      short loc_180022423
0x180022414  mov     rax, [rdi]
0x180022417  mov     rcx, rdi
0x18002241a  mov     rax, [rax+8]
0x18002241e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022423  mov     rdx, [rbp+ppvObject]; struct IXmlWriter *
0x180022427  mov     rcx, r14; this
0x18002242a  call    ?Write@CTpRequestMessage@@QEAAJPEAUIXmlWriter@@@Z; CTpRequestMessage::Write(IXmlWriter *)
0x18002242f  mov     ebx, eax
0x180022431  call    cs:__imp_GetTickCount
0x180022438  nop     dword ptr [rax+rax+00h]
0x18002243d  sub     eax, r15d
0x180022440  mov     rcx, [rbp+arg_20]
0x180022444  mov     [rcx], eax
0x180022446  mov     [rsi], ebx
0x180022448  test    ebx, ebx
0x18002244a  jns     short loc_18002248C
0x18002244c  test    rdi, rdi
0x18002244f  jz      short loc_180022462
0x180022451  mov     rax, [rdi]
0x180022454  mov     edx, ebx
0x180022456  mov     rcx, rdi
0x180022459  mov     rax, [rax+10h]
0x18002245d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022462  lea     rdx, WPP_GLOBAL_Control
0x180022469  mov     rcx, cs:WPP_GLOBAL_Control
0x180022470  cmp     rcx, rdx
0x180022473  jz      loc_1800224FB
0x180022479  test    [rcx+1Ch], r13b
0x18002247d  jz      short loc_1800224FB
0x18002247f  mov     edx, 24h ; '$'
0x180022484  mov     r9d, ebx
0x180022487  jmp     loc_180022297
0x18002248c  mov     rcx, [rbp+ppvObject]
0x180022490  mov     rax, [rcx]
0x180022493  mov     rax, [rax+0F8h]
0x18002249a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002249f  mov     ebx, eax
0x1800224a1  test    eax, eax
0x1800224a3  jns     short loc_1800224C8
0x1800224a5  lea     rdx, WPP_GLOBAL_Control
0x1800224ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224b3  cmp     rcx, rdx
0x1800224b6  jz      short loc_1800224FB
0x1800224b8  test    [rcx+1Ch], r13b
0x1800224bc  jz      short loc_1800224FB
0x1800224be  mov     edx, 25h ; '%'
0x1800224c3  jmp     loc_180022294
0x1800224c8  mov     rcx, [rbp+ppvObject]
0x1800224cc  mov     [rbp+ppvObject], 0
0x1800224d4  test    rcx, rcx
0x1800224d7  jz      short loc_1800224E6
0x1800224d9  mov     rax, [rcx]
0x1800224dc  mov     rax, [rax+10h]
0x1800224e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224e5  nop
0x1800224e6  test    rdi, rdi
0x1800224e9  jz      short loc_1800224FB
0x1800224eb  mov     rax, [rdi]
0x1800224ee  mov     rcx, rdi
0x1800224f1  mov     rax, [rax+18h]
0x1800224f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224fa  nop
0x1800224fb  mov     rcx, [rbp+ppvObject]
0x1800224ff  test    rcx, rcx
0x180022502  jz      short loc_180022511
0x180022504  mov     rax, [rcx]
0x180022507  mov     rax, [rax+10h]
0x18002250b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022510  nop
0x180022511  lea     rax, ??_7CIStreamAdapter@@6B@; const CIStreamAdapter::`vftable'
0x180022518  mov     [rbp+var_18], rax
0x18002251c  cmp     [rbp+var_8], r13d
0x180022520  jz      short loc_180022528
0x180022522  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022527  nop
0x180022528  mov     eax, ebx
0x18002252a  add     rsp, 40h
0x18002252e  pop     r15
0x180022530  pop     r14
0x180022532  pop     r13
0x180022534  pop     rdi
0x180022535  pop     rsi
0x180022536  pop     rbx
0x180022537  pop     rbp
0x180022538  retn
```
