# CTpTransport::BuildRequestXML(CTpRequestMessage *,ITpCallbacks *,CMemoryByteStream &,long &,ulong &)

- ea: `0x180021678`
- end: `0x1800219bb`
- name: `?BuildRequestXML@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUITpCallbacks@@AEAVCMemoryByteStream@@AEAJAEAK@Z`
- size: `835`
- prototype: `__int64 __usercall@<rax>(struct CTpRequestMessage *this@<rcx>, struct ITpCallbacks *@<rdx>, struct CMemoryByteStream *@<r8>, int *@<r9>, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c24c`
- `0x180082e00`
- `0x180086d50`

## callees

- `0x18001fe24`
- `0x180021678`
- `0x1800219c4`
- `0x18003bf14`
- `0x180046674`
- `0x18004c614`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800216b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800218b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800216b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800218b9`
- `XmlLite!CreateXmlWriter` at `0x1800216e5`
- `XmlLite!CreateXmlWriter` at `0x1800216e5`

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
  unsigned int v11; // ebx
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  void *v15; // rcx
  void *ppvObject; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-18h] BYREF
  int v19; // [rsp+38h] [rbp-8h]

  CIStreamAdapter::CIStreamAdapter((CIStreamAdapter *)v18, a3);
  CMemoryByteStream::OpenForReadWrite(v8);
  TickCount = GetTickCount();
  ppvObject = 0;
  v10 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2, 1);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 2);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(void *, _QWORD *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v18);
          v11 = v10;
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 208LL))(ppvObject, 1);
            v11 = v10;
            if ( v10 >= 0 )
            {
              if ( a2 )
                (*(void (__fastcall **)(struct ITpCallbacks *))(*(_QWORD *)a2 + 8LL))(a2);
              v11 = CTpRequestMessage::Write(this, (struct IXmlWriter *)ppvObject);
              *a5 = GetTickCount() - TickCount;
              *a4 = v11;
              if ( (v11 & 0x80000000) == 0 )
              {
                v10 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                v11 = v10;
                if ( v10 >= 0 )
                {
                  v15 = ppvObject;
                  ppvObject = 0;
                  if ( v15 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
                  if ( a2 )
                    (*(void (__fastcall **)(struct ITpCallbacks *))(*(_QWORD *)a2 + 24LL))(a2);
                }
                else
                {
                  v12 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v13 = 37;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                if ( a2 )
                  (*(void (__fastcall **)(struct ITpCallbacks *, _QWORD))(*(_QWORD *)a2 + 16LL))(a2, v11);
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v13 = 36;
                  v14 = v11;
                  goto LABEL_6;
                }
              }
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v13 = 35;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v13 = 34;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v13 = 33;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v13 = 32;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 31;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 30;
LABEL_5:
      v14 = (unsigned int)v10;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v14);
    }
  }
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  v18[0] = &CIStreamAdapter::`vftable';
  if ( v19 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return v11;
}

```

## disassembly

```asm
0x180021678  push    rbp
0x18002167a  push    rbx
0x18002167b  push    rsi
0x18002167c  push    rdi
0x18002167d  push    r13
0x18002167f  push    r14
0x180021681  push    r15
0x180021683  mov     rbp, rsp
0x180021686  sub     rsp, 40h
0x18002168a  mov     rsi, r9
0x18002168d  mov     rdi, rdx
0x180021690  mov     r14, rcx
0x180021693  mov     rdx, r8; struct IWerByteStream *
0x180021696  lea     rcx, [rbp+var_18]; this
0x18002169a  call    ??0CIStreamAdapter@@QEAA@PEAUIWerByteStream@@@Z; CIStreamAdapter::CIStreamAdapter(IWerByteStream *)
0x18002169f  nop
0x1800216a0  mov     [rbp+ppvObject], 0
0x1800216a8  mov     rcx, r8; this
0x1800216ab  call    ?OpenForReadWrite@CMemoryByteStream@@QEAAXXZ; CMemoryByteStream::OpenForReadWrite(void)
0x1800216b0  call    cs:__imp_GetTickCount
0x1800216b6  mov     r15d, eax
0x1800216b9  mov     rcx, [rbp+ppvObject]
0x1800216bd  mov     [rbp+ppvObject], 0
0x1800216c5  test    rcx, rcx
0x1800216c8  jz      short loc_1800216D7
0x1800216ca  mov     rdx, [rcx]
0x1800216cd  mov     rax, [rdx+10h]
0x1800216d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216d6  nop
0x1800216d7  xor     r8d, r8d; pMalloc
0x1800216da  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800216de  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1800216e5  call    cs:__imp_CreateXmlWriter
0x1800216eb  mov     ebx, eax
0x1800216ed  mov     r13d, 1
0x1800216f3  test    eax, eax
0x1800216f5  jns     short loc_180021734
0x1800216f7  lea     rdx, WPP_GLOBAL_Control
0x1800216fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180021705  cmp     rcx, rdx
0x180021708  jz      loc_18002197D
0x18002170e  test    [rcx+1Ch], r13b
0x180021712  jz      loc_18002197D
0x180021718  lea     edx, [r13+1Dh]
0x18002171c  mov     r9d, eax
0x18002171f  lea     r8, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids
0x180021726  mov     rcx, [rcx+10h]
0x18002172a  call    WPP_SF_d
0x18002172f  jmp     loc_18002197D
0x180021734  mov     rcx, [rbp+ppvObject]
0x180021738  mov     rax, [rcx]
0x18002173b  mov     r8, r13
0x18002173e  mov     edx, 2
0x180021743  mov     rax, [rax+28h]
0x180021747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002174c  mov     ebx, eax
0x18002174e  test    eax, eax
0x180021750  jns     short loc_18002177A
0x180021752  lea     rdx, WPP_GLOBAL_Control
0x180021759  mov     rcx, cs:WPP_GLOBAL_Control
0x180021760  cmp     rcx, rdx
0x180021763  jz      loc_18002197D
0x180021769  test    [rcx+1Ch], r13b
0x18002176d  jz      loc_18002197D
0x180021773  mov     edx, 1Fh
0x180021778  jmp     short loc_18002171C
0x18002177a  mov     rcx, [rbp+ppvObject]
0x18002177e  mov     rax, [rcx]
0x180021781  mov     r8, r13
0x180021784  mov     edx, r13d
0x180021787  mov     rax, [rax+28h]
0x18002178b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021790  mov     ebx, eax
0x180021792  test    eax, eax
0x180021794  jns     short loc_1800217C1
0x180021796  lea     rdx, WPP_GLOBAL_Control
0x18002179d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217a4  cmp     rcx, rdx
0x1800217a7  jz      loc_18002197D
0x1800217ad  test    [rcx+1Ch], r13b
0x1800217b1  jz      loc_18002197D
0x1800217b7  mov     edx, 20h ; ' '
0x1800217bc  jmp     loc_18002171C
0x1800217c1  mov     rcx, [rbp+ppvObject]
0x1800217c5  mov     rax, [rcx]
0x1800217c8  mov     edx, 4
0x1800217cd  lea     r8d, [rdx-2]
0x1800217d1  mov     rax, [rax+28h]
0x1800217d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217da  mov     ebx, eax
0x1800217dc  test    eax, eax
0x1800217de  jns     short loc_18002180B
0x1800217e0  lea     rdx, WPP_GLOBAL_Control
0x1800217e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217ee  cmp     rcx, rdx
0x1800217f1  jz      loc_18002197D
0x1800217f7  test    [rcx+1Ch], r13b
0x1800217fb  jz      loc_18002197D
0x180021801  mov     edx, 21h ; '!'
0x180021806  jmp     loc_18002171C
0x18002180b  mov     rcx, [rbp+ppvObject]
0x18002180f  mov     rax, [rcx]
0x180021812  lea     rdx, [rbp+var_18]
0x180021816  mov     rax, [rax+18h]
0x18002181a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002181f  mov     ebx, eax
0x180021821  test    eax, eax
0x180021823  jns     short loc_180021850
0x180021825  lea     rdx, WPP_GLOBAL_Control
0x18002182c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021833  cmp     rcx, rdx
0x180021836  jz      loc_18002197D
0x18002183c  test    [rcx+1Ch], r13b
0x180021840  jz      loc_18002197D
0x180021846  mov     edx, 22h ; '"'
0x18002184b  jmp     loc_18002171C
0x180021850  mov     rcx, [rbp+ppvObject]
0x180021854  mov     rax, [rcx]
0x180021857  mov     edx, r13d
0x18002185a  mov     rax, [rax+0D0h]
0x180021861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021866  mov     ebx, eax
0x180021868  test    eax, eax
0x18002186a  jns     short loc_180021897
0x18002186c  lea     rdx, WPP_GLOBAL_Control
0x180021873  mov     rcx, cs:WPP_GLOBAL_Control
0x18002187a  cmp     rcx, rdx
0x18002187d  jz      loc_18002197D
0x180021883  test    [rcx+1Ch], r13b
0x180021887  jz      loc_18002197D
0x18002188d  mov     edx, 23h ; '#'
0x180021892  jmp     loc_18002171C
0x180021897  test    rdi, rdi
0x18002189a  jz      short loc_1800218AB
0x18002189c  mov     rax, [rdi]
0x18002189f  mov     rcx, rdi
0x1800218a2  mov     rax, [rax+8]
0x1800218a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ab  mov     rdx, [rbp+ppvObject]; struct IXmlWriter *
0x1800218af  mov     rcx, r14; this
0x1800218b2  call    ?Write@CTpRequestMessage@@QEAAJPEAUIXmlWriter@@@Z; CTpRequestMessage::Write(IXmlWriter *)
0x1800218b7  mov     ebx, eax
0x1800218b9  call    cs:__imp_GetTickCount
0x1800218bf  sub     eax, r15d
0x1800218c2  mov     rcx, [rbp+arg_20]
0x1800218c6  mov     [rcx], eax
0x1800218c8  mov     [rsi], ebx
0x1800218ca  test    ebx, ebx
0x1800218cc  jns     short loc_18002190E
0x1800218ce  test    rdi, rdi
0x1800218d1  jz      short loc_1800218E4
0x1800218d3  mov     rax, [rdi]
0x1800218d6  mov     edx, ebx
0x1800218d8  mov     rcx, rdi
0x1800218db  mov     rax, [rax+10h]
0x1800218df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218e4  lea     rdx, WPP_GLOBAL_Control
0x1800218eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218f2  cmp     rcx, rdx
0x1800218f5  jz      loc_18002197D
0x1800218fb  test    [rcx+1Ch], r13b
0x1800218ff  jz      short loc_18002197D
0x180021901  mov     edx, 24h ; '$'
0x180021906  mov     r9d, ebx
0x180021909  jmp     loc_18002171F
0x18002190e  mov     rcx, [rbp+ppvObject]
0x180021912  mov     rax, [rcx]
0x180021915  mov     rax, [rax+0F8h]
0x18002191c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021921  mov     ebx, eax
0x180021923  test    eax, eax
0x180021925  jns     short loc_18002194A
0x180021927  lea     rdx, WPP_GLOBAL_Control
0x18002192e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021935  cmp     rcx, rdx
0x180021938  jz      short loc_18002197D
0x18002193a  test    [rcx+1Ch], r13b
0x18002193e  jz      short loc_18002197D
0x180021940  mov     edx, 25h ; '%'
0x180021945  jmp     loc_18002171C
0x18002194a  mov     rcx, [rbp+ppvObject]
0x18002194e  mov     [rbp+ppvObject], 0
0x180021956  test    rcx, rcx
0x180021959  jz      short loc_180021968
0x18002195b  mov     rax, [rcx]
0x18002195e  mov     rax, [rax+10h]
0x180021962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021967  nop
0x180021968  test    rdi, rdi
0x18002196b  jz      short loc_18002197D
0x18002196d  mov     rax, [rdi]
0x180021970  mov     rcx, rdi
0x180021973  mov     rax, [rax+18h]
0x180021977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002197c  nop
0x18002197d  mov     rcx, [rbp+ppvObject]
0x180021981  test    rcx, rcx
0x180021984  jz      short loc_180021993
0x180021986  mov     rax, [rcx]
0x180021989  mov     rax, [rax+10h]
0x18002198d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021992  nop
0x180021993  lea     rax, ??_7CIStreamAdapter@@6B@; const CIStreamAdapter::`vftable'
0x18002199a  mov     [rbp+var_18], rax
0x18002199e  cmp     [rbp+var_8], r13d
0x1800219a2  jz      short loc_1800219AA
0x1800219a4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800219a9  nop
0x1800219aa  mov     eax, ebx
0x1800219ac  add     rsp, 40h
0x1800219b0  pop     r15
0x1800219b2  pop     r14
0x1800219b4  pop     r13
0x1800219b6  pop     rdi
0x1800219b7  pop     rsi
0x1800219b8  pop     rbx
0x1800219b9  pop     rbp
0x1800219ba  retn
```
