# CWSHRemote::DoScript(void)

- ea: `0x140002310`
- end: `0x1400024e8`
- name: `?DoScript@CWSHRemote@@AEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(WPARAM wParam)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140002d50`

## callees

- `0x140001008`
- `0x140001048`
- `0x14000169c`
- `0x140001864`
- `0x140002310`
- `0x1400026e8`
- `0x14000566c`
- `0x140008950`
- `0x14000919c`
- `0x140014330`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002323`
- `KERNEL32!GetCurrentThreadId` at `0x140002323`
- `ole32!CoGetInterfaceAndReleaseStream` at `0x140002367`
- `ole32!CoGetInterfaceAndReleaseStream` at `0x140002367`

## pseudocode

```c
__int64 __fastcall CWSHRemote::DoScript(WPARAM wParam)
{
  int v1; // ebx
  IStream *v4; // rcx
  const unsigned __int16 **v5; // r14
  HRESULT InterfaceAndReleaseStream; // eax
  unsigned int v7; // ebx
  wchar_t *v8; // rcx
  unsigned int v9; // eax
  int v10; // ebx
  void *v11; // rax
  CWinHost *v12; // rax
  __int64 v13; // rax
  HINSTANCE v14; // rdx
  int v15; // r15d
  void *v16; // rbx
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(wParam + 36);
  if ( GetCurrentThreadId() != v1 )
    return 2147549183LL;
  if ( !*(_BYTE *)(wParam + 161) || *(_BYTE *)(wParam + 160) )
    return 2147942414LL;
  v4 = *(IStream **)(wParam + 112);
  v5 = 0;
  ppv = 0;
  InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v4, &IID_IMoniker, &ppv);
  *(_QWORD *)(wParam + 112) = 0;
  v7 = InterfaceAndReleaseStream;
  if ( InterfaceAndReleaseStream >= 0 )
  {
    v8 = *(wchar_t **)(wParam + 96);
    if ( !v8 )
    {
LABEL_7:
      v7 = -2147467259;
      goto LABEL_19;
    }
    v9 = SplitCommandLine(v8, 0);
    v10 = v9 + 1;
    v11 = operator new(saturated_mul((int)(v9 + 2), 8u));
    v5 = (const unsigned __int16 **)v11;
    if ( v11 )
    {
      SplitCommandLine(*(wchar_t **)(wParam + 96), (unsigned __int16 **)v11 + 1);
      *v5 = L"wscript";
      v5[v10] = 0;
      if ( !(unsigned int)CCriticalSection::Enter((CCriticalSection *)(wParam + 120)) )
        goto LABEL_7;
      v12 = (CWinHost *)operator new(0x2F0u);
      if ( v12 )
        v12 = CWinHost::CWinHost(v12);
      *(_QWORD *)(wParam + 104) = v12;
      CCriticalSection::Leave((CCriticalSection *)(wParam + 120));
      v13 = *(_QWORD *)(wParam + 104);
      if ( v13 )
      {
        *(_QWORD *)(v13 + 744) = wParam;
        *(_BYTE *)(v13 + 75) = 1;
        CWSHRemote::FireEvent(wParam, 1);
        v15 = CHost::Main(*(CHost **)(wParam + 104), v14, v10, v5, (struct IMoniker *)ppv);
        CWSHRemote::FireEvent(wParam, 2);
        if ( (unsigned int)CCriticalSection::Enter((CCriticalSection *)(wParam + 120)) )
        {
          v16 = *(void **)(wParam + 104);
          if ( v16 )
          {
            CHost::~CHost(*(CHost **)(wParam + 104));
            operator delete(v16);
          }
          *(_QWORD *)(wParam + 104) = 0;
          CCriticalSection::Leave((CCriticalSection *)(wParam + 120));
        }
        v7 = v15 != 0 ? 0x80004005 : 0;
        goto LABEL_19;
      }
    }
    v7 = -2147024882;
  }
LABEL_19:
  _InterlockedExchange((volatile __int32 *)(wParam + 44), 2);
  if ( v5 )
    operator delete(v5);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v7;
}

```

## disassembly

```asm
0x140002310  push    rbx
0x140002312  push    rbp
0x140002313  push    rsi
0x140002314  push    rdi
0x140002315  push    r14
0x140002317  push    r15
0x140002319  sub     rsp, 38h
0x14000231d  mov     ebx, [rcx+24h]
0x140002320  mov     rdi, rcx
0x140002323  call    cs:__imp_GetCurrentThreadId
0x140002329  cmp     eax, ebx
0x14000232b  jz      short loc_140002337
0x14000232d  mov     eax, 8000FFFFh
0x140002332  jmp     loc_1400024DB
0x140002337  lea     rsi, [rdi+78h]
0x14000233b  cmp     byte ptr [rsi+29h], 0
0x14000233f  jz      loc_1400024D6
0x140002345  cmp     byte ptr [rsi+28h], 0
0x140002349  jnz     loc_1400024D6
0x14000234f  mov     rcx, [rdi+70h]; pStm
0x140002353  lea     r8, [rsp+68h+ppv]; ppv
0x140002358  xor     r14d, r14d
0x14000235b  lea     rdx, IID_IMoniker; iid
0x140002362  mov     [rsp+68h+ppv], r14
0x140002367  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x14000236d  mov     [rdi+70h], r14
0x140002371  lea     ebp, [r14+2]
0x140002375  mov     ebx, eax
0x140002377  test    eax, eax
0x140002379  js      loc_1400024AC
0x14000237f  mov     rcx, [rdi+60h]; Destination
0x140002383  test    rcx, rcx
0x140002386  jnz     short loc_140002392
0x140002388  mov     ebx, 80004005h
0x14000238d  jmp     loc_1400024AC
0x140002392  xor     edx, edx; unsigned __int16 **
0x140002394  call    ?SplitCommandLine@@YAIPEAGPEAPEAG@Z; SplitCommandLine(ushort *,ushort * *)
0x140002399  lea     ebx, [rax+1]
0x14000239c  lea     eax, [rbx+1]
0x14000239f  movsxd  rcx, eax
0x1400023a2  mov     eax, 8
0x1400023a7  mul     rcx
0x1400023aa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400023b1  cmovb   rax, rcx
0x1400023b5  mov     rcx, rax; Size
0x1400023b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400023bd  mov     r14, rax
0x1400023c0  test    rax, rax
0x1400023c3  jnz     short loc_1400023CF
0x1400023c5  mov     ebx, 8007000Eh
0x1400023ca  jmp     loc_1400024AC
0x1400023cf  mov     rcx, [rdi+60h]; Destination
0x1400023d3  lea     rdx, [rax+8]; unsigned __int16 **
0x1400023d7  call    ?SplitCommandLine@@YAIPEAGPEAPEAG@Z; SplitCommandLine(ushort *,ushort * *)
0x1400023dc  lea     rax, aWscript; "wscript"
0x1400023e3  mov     rcx, rsi; this
0x1400023e6  mov     [r14], rax
0x1400023e9  movsxd  rax, ebx
0x1400023ec  mov     qword ptr [r14+rax*8], 0
0x1400023f4  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x1400023f9  test    eax, eax
0x1400023fb  jz      short loc_140002388
0x1400023fd  mov     ecx, 2F0h; Size
0x140002402  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002407  test    rax, rax
0x14000240a  jz      short loc_140002414
0x14000240c  mov     rcx, rax; this
0x14000240f  call    ??0CWinHost@@QEAA@XZ; CWinHost::CWinHost(void)
0x140002414  mov     rcx, rsi; this
0x140002417  mov     [rdi+68h], rax
0x14000241b  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x140002420  mov     rax, [rdi+68h]
0x140002424  test    rax, rax
0x140002427  jz      short loc_1400023C5
0x140002429  mov     edx, 1; int
0x14000242e  mov     [rax+2E8h], rdi
0x140002435  mov     rcx, rdi; wParam
0x140002438  mov     byte ptr [rax+4Bh], 1
0x14000243c  call    ?FireEvent@CWSHRemote@@QEAAXJ@Z; CWSHRemote::FireEvent(long)
0x140002441  mov     rax, [rsp+68h+ppv]
0x140002446  mov     r9, r14; unsigned __int16 **
0x140002449  mov     rcx, [rdi+68h]; this
0x14000244d  mov     r8d, ebx; int
0x140002450  mov     [rsp+68h+var_48], rax; struct IMoniker *
0x140002455  call    ?Main@CHost@@QEAAHPEAUHINSTANCE__@@HPEAPEBGPEAUIMoniker@@@Z; CHost::Main(HINSTANCE__ *,int,ushort const * *,IMoniker *)
0x14000245a  mov     edx, ebp; int
0x14000245c  mov     rcx, rdi; wParam
0x14000245f  mov     r15d, eax
0x140002462  call    ?FireEvent@CWSHRemote@@QEAAXJ@Z; CWSHRemote::FireEvent(long)
0x140002467  mov     rcx, rsi; this
0x14000246a  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x14000246f  test    eax, eax
0x140002471  jz      short loc_14000249C
0x140002473  mov     rbx, [rdi+68h]
0x140002477  test    rbx, rbx
0x14000247a  jz      short loc_14000248C
0x14000247c  mov     rcx, rbx; this
0x14000247f  call    ??1CHost@@QEAA@XZ; CHost::~CHost(void)
0x140002484  mov     rcx, rbx; Block
0x140002487  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000248c  mov     rcx, rsi; this
0x14000248f  mov     qword ptr [rdi+68h], 0
0x140002497  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x14000249c  xor     eax, eax
0x14000249e  mov     ebx, 80004005h
0x1400024a3  sub     eax, r15d
0x1400024a6  neg     eax
0x1400024a8  sbb     eax, eax
0x1400024aa  and     ebx, eax
0x1400024ac  xchg    ebp, [rdi+2Ch]
0x1400024af  test    r14, r14
0x1400024b2  jz      short loc_1400024BC
0x1400024b4  mov     rcx, r14; Block
0x1400024b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400024bc  mov     rcx, [rsp+68h+ppv]
0x1400024c1  test    rcx, rcx
0x1400024c4  jz      short loc_1400024D2
0x1400024c6  mov     rax, [rcx]
0x1400024c9  mov     rax, [rax+10h]
0x1400024cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024d2  mov     eax, ebx
0x1400024d4  jmp     short loc_1400024DB
0x1400024d6  mov     eax, 8007000Eh
0x1400024db  add     rsp, 38h
0x1400024df  pop     r15
0x1400024e1  pop     r14
0x1400024e3  pop     rdi
0x1400024e4  pop     rsi
0x1400024e5  pop     rbp
0x1400024e6  pop     rbx
0x1400024e7  retn
```
