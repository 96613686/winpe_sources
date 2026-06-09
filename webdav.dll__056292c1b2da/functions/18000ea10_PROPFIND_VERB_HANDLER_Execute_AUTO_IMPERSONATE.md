# PROPFIND_VERB_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x18000ea10`
- end: `0x18000ec2b`
- name: `?Execute@PROPFIND_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180002e60`
- `0x1800033d4`
- `0x180003634`
- `0x180003860`
- `0x1800056ac`
- `0x180005a5c`
- `0x18000ea10`
- `0x18001dea0`
- `0x180020614`
- `0x1800206ec`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000ea53`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000ea53`

## string_xrefs

- `0x18000eb06`: `Invalid Depth: For PROPFIND Not Allowed Due To Configuration`

## pseudocode

```c
__int64 __fastcall PROPFIND_VERB_HANDLER::Execute(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // eax
  int ConstrainedDepth; // eax
  unsigned int v5; // edi
  unsigned __int16 v6; // r9
  const char *v7; // r8
  unsigned __int16 v8; // dx
  int v9; // ecx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  _BYTE v14[5008]; // [rsp+50h] [rbp-13A8h] BYREF

  LOCK_SET::LOCK_SET((LOCK_SET *)v14);
  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  v2 = 1;
  XML_RESPONDER::Initialize(
    (XML_RESPONDER *)(a1 + 448),
    *(struct IHttpContext **)(a1 + 8),
    (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL) >> 2) & 1);
  v3 = *(_DWORD *)(a1 + 208);
  if ( v3 == -1 || (v3 & 0x10) == 0 )
    v2 = 0;
  ConstrainedDepth = GetConstrainedDepth(*(_QWORD *)(a1 + 8), v2);
  *(_DWORD *)(a1 + 6044) = ConstrainedDepth;
  v5 = 2;
  if ( ConstrainedDepth == -1 )
  {
    v6 = 2;
    v7 = "Bad Request";
    v8 = 400;
LABEL_8:
    DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, v8, v7, v6, 0);
    goto LABEL_20;
  }
  v9 = *(_DWORD *)(a1 + 208);
  if ( v9 == -1 || (v9 & 0x10) == 0 )
  {
    *(_DWORD *)(a1 + 6044) = 0;
  }
  else if ( ConstrainedDepth == 2 && !*(_DWORD *)(*(_QWORD *)(a1 + 24) + 44LL) )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v10 + 32LL))(
      v10,
      L"Invalid Depth: For PROPFIND Not Allowed Due To Configuration",
      0,
      0,
      3);
    v8 = 403;
    v7 = "Forbidden";
    v6 = 22;
    goto LABEL_8;
  }
  if ( (unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                       (DAV_BASE_HANDLER *)a1,
                       *(struct IHttpFileInfo **)(a1 + 32)) )
  {
    v11 = HandleDavIfAndLocks(
            *(struct IHttpContext **)(a1 + 8),
            *(struct DAV_LOCK_STORE **)(*(_QWORD *)(a1 + 24) + 3328LL),
            *(const unsigned __int16 **)(a1 + 72),
            (struct LOCK_SET *)v14,
            0,
            0,
            0,
            0,
            3u);
    if ( v11 >= 0
      && (v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 240) + 8LL))(*(_QWORD *)(a1 + 240), -1),
          v11 >= 0) )
    {
      v12 = *(_QWORD *)(a1 + 8);
      *(_DWORD *)(a1 + 440) = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 12LL);
      *(_QWORD *)(a1 + 304) = v12;
      *(_QWORD *)(a1 + 312) = a1 + 432;
      *(_QWORD *)(a1 + 320) = 0;
      *(_QWORD *)(a1 + 328) = a1 + 296;
      *(_QWORD *)(a1 + 336) = -1;
      *(_QWORD *)(a1 + 344) = 0;
      *(_DWORD *)(a1 + 352) = 0;
      v5 = CAsyncReader::StartRead();
    }
    else
    {
      DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v11);
    }
  }
LABEL_20:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v14);
  return v5;
}

```

## disassembly

```asm
0x18000ea10  mov     [rsp+arg_8], rbx
0x18000ea15  mov     [rsp+arg_10], rsi
0x18000ea1a  push    rdi
0x18000ea1b  mov     eax, 13F0h
0x18000ea20  call    _alloca_probe
0x18000ea25  sub     rsp, rax
0x18000ea28  mov     rax, cs:__security_cookie
0x18000ea2f  xor     rax, rsp
0x18000ea32  mov     [rsp+13F8h+var_18], rax
0x18000ea3a  mov     rbx, rcx
0x18000ea3d  lea     rcx, [rsp+13F8h+var_13A8]; this
0x18000ea42  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x18000ea47  test    cs:g_dwDebugFlags, 40000000h
0x18000ea51  jz      short loc_18000EA59
0x18000ea53  call    cs:__imp_DebugBreak
0x18000ea59  mov     rax, [rbx+18h]
0x18000ea5d  lea     rcx, [rbx+1C0h]; this
0x18000ea64  mov     rdx, [rbx+8]; struct IHttpContext *
0x18000ea68  mov     edi, 1
0x18000ea6d  mov     r8d, [rax+8]
0x18000ea71  shr     r8d, 2
0x18000ea75  and     r8d, edi; int
0x18000ea78  call    ?Initialize@XML_RESPONDER@@QEAAXPEAVIHttpContext@@H@Z; XML_RESPONDER::Initialize(IHttpContext *,int)
0x18000ea7d  mov     eax, [rbx+0D0h]
0x18000ea83  xor     esi, esi
0x18000ea85  cmp     eax, 0FFFFFFFFh
0x18000ea88  jz      short loc_18000EA8E
0x18000ea8a  test    al, 10h
0x18000ea8c  jnz     short loc_18000EA90
0x18000ea8e  mov     edi, esi
0x18000ea90  mov     rcx, [rbx+8]
0x18000ea94  mov     edx, edi
0x18000ea96  call    ?GetConstrainedDepth@@YA?AW4DAV_DEPTH@@PEAVIHttpContext@@H@Z; GetConstrainedDepth(IHttpContext *,int)
0x18000ea9b  mov     [rbx+179Ch], eax
0x18000eaa1  mov     edi, 2
0x18000eaa6  cmp     eax, 0FFFFFFFFh
0x18000eaa9  jnz     short loc_18000EACB
0x18000eaab  mov     r9d, edi; unsigned __int16
0x18000eaae  lea     r8, aBadRequest; "Bad Request"
0x18000eab5  mov     edx, 190h; unsigned __int16
0x18000eaba  mov     rcx, rbx; this
0x18000eabd  mov     [rsp+13F8h+var_13D8], esi; int
0x18000eac1  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000eac6  jmp     loc_18000EBFA
0x18000eacb  mov     ecx, [rbx+0D0h]
0x18000ead1  cmp     ecx, 0FFFFFFFFh
0x18000ead4  jz      short loc_18000EB33
0x18000ead6  test    cl, 10h
0x18000ead9  jz      short loc_18000EB33
0x18000eadb  cmp     eax, edi
0x18000eadd  jnz     short loc_18000EB39
0x18000eadf  mov     rax, [rbx+18h]
0x18000eae3  cmp     [rax+2Ch], esi
0x18000eae6  jnz     short loc_18000EB39
0x18000eae8  mov     rcx, [rbx+8]
0x18000eaec  mov     rax, [rcx]
0x18000eaef  mov     rax, [rax+110h]
0x18000eaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eafb  mov     r10, rax
0x18000eafe  mov     byte ptr [rsp+13F8h+var_13D8], 3
0x18000eb03  xor     r9d, r9d
0x18000eb06  lea     rdx, aInvalidDepthFo; "Invalid Depth: For PROPFIND Not Allowed"...
0x18000eb0d  xor     r8d, r8d
0x18000eb10  mov     rcx, [rax]
0x18000eb13  mov     rax, [rcx+20h]
0x18000eb17  mov     rcx, r10
0x18000eb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb1f  mov     edx, 193h
0x18000eb24  lea     r8, aForbidden; "Forbidden"
0x18000eb2b  mov     r9d, 16h
0x18000eb31  jmp     short loc_18000EABA
0x18000eb33  mov     [rbx+179Ch], esi
0x18000eb39  mov     rdx, [rbx+20h]; struct IHttpFileInfo *
0x18000eb3d  mov     rcx, rbx; this
0x18000eb40  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x18000eb45  test    eax, eax
0x18000eb47  jz      loc_18000EBFA
0x18000eb4d  mov     rdx, [rbx+18h]
0x18000eb51  lea     r9, [rsp+13F8h+var_13A8]; struct LOCK_SET *
0x18000eb56  mov     r8, [rbx+48h]; unsigned __int16 *
0x18000eb5a  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000eb5e  mov     [rsp+13F8h+var_13B8], 3; unsigned int
0x18000eb66  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x18000eb6d  mov     [rsp+13F8h+var_13C0], esi; int
0x18000eb71  mov     [rsp+13F8h+var_13C8], rsi; struct LOCK_SET *
0x18000eb76  mov     [rsp+13F8h+var_13D0], rsi; unsigned __int16 *
0x18000eb7b  mov     [rsp+13F8h+var_13D8], esi; int
0x18000eb7f  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x18000eb84  test    eax, eax
0x18000eb86  js      short loc_18000EBA3
0x18000eb88  mov     rcx, [rbx+0F0h]
0x18000eb8f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000eb93  mov     rax, [rcx]
0x18000eb96  mov     rax, [rax+8]
0x18000eb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb9f  test    eax, eax
0x18000eba1  jns     short loc_18000EBAF
0x18000eba3  mov     edx, eax; int
0x18000eba5  mov     rcx, rbx; this
0x18000eba8  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000ebad  jmp     short loc_18000EBFA
0x18000ebaf  mov     rax, [rbx+18h]
0x18000ebb3  lea     rdx, [rbx+128h]
0x18000ebba  mov     ecx, [rax+0Ch]
0x18000ebbd  mov     rax, [rbx+8]
0x18000ebc1  mov     [rbx+1B8h], ecx
0x18000ebc7  lea     rcx, [rbx+130h]
0x18000ebce  mov     [rcx], rax
0x18000ebd1  lea     rax, [rbx+1B0h]
0x18000ebd8  mov     [rcx+8], rax
0x18000ebdc  mov     [rcx+10h], rsi
0x18000ebe0  mov     [rcx+18h], rdx
0x18000ebe4  mov     qword ptr [rcx+20h], 0FFFFFFFFFFFFFFFFh
0x18000ebec  mov     [rcx+28h], rsi
0x18000ebf0  mov     [rcx+30h], esi
0x18000ebf3  call    ?StartRead@CAsyncReader@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; CAsyncReader::StartRead(void)
0x18000ebf8  mov     edi, eax
0x18000ebfa  lea     rcx, [rsp+13F8h+var_13A8]; this
0x18000ebff  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000ec04  mov     eax, edi
0x18000ec06  mov     rcx, [rsp+13F8h+var_18]
0x18000ec0e  xor     rcx, rsp; StackCookie
0x18000ec11  call    __security_check_cookie
0x18000ec16  lea     r11, [rsp+13F8h+var_8]
0x18000ec1e  mov     rbx, [r11+18h]
0x18000ec22  mov     rsi, [r11+20h]
0x18000ec26  mov     rsp, r11
0x18000ec29  pop     rdi
0x18000ec2a  retn
```
