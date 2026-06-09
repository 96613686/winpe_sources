# LOCK_VERB_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x18000c600`
- end: `0x18000c7cd`
- name: `?Execute@LOCK_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180002e60`
- `0x1800033d4`
- `0x180003634`
- `0x180003860`
- `0x1800056ac`
- `0x180005a5c`
- `0x180007540`
- `0x18000c600`
- `0x18001dea0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000c61e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000c61e`

## pseudocode

```c
__int64 __fastcall LOCK_VERB_HANDLER::Execute(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  unsigned __int16 v4; // r9
  unsigned __int16 v5; // dx
  const char *v6; // r8
  int v7; // eax
  __int64 v8; // rdx
  int ConstrainedDepth; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax

  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  v2 = *(_QWORD *)(a1 + 24);
  if ( !*(_DWORD *)(v2 + 52) || (v3 = *(_QWORD *)(v2 + 3328), !*(_DWORD *)(v3 + 28)) )
  {
    v5 = 501;
    v6 = "Not Implemented";
    goto LABEL_22;
  }
  if ( (int)ValidateTimeoutHeader(
              *(struct IHttpContext **)(a1 + 8),
              (unsigned __int64 *)(a1 + 560),
              (const char **)(a1 + 5576)) < 0 )
  {
    v4 = 8;
LABEL_7:
    v5 = 400;
    v6 = "Bad Request";
LABEL_23:
    DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, v5, v6, v4, 0);
    return 2;
  }
  v7 = *(_DWORD *)(a1 + 208);
  if ( v7 == -1 || (v8 = 1, (v7 & 0x10) == 0) )
    v8 = 0;
  ConstrainedDepth = GetConstrainedDepth(*(_QWORD *)(a1 + 8), v8);
  *(_DWORD *)(a1 + 552) = ConstrainedDepth;
  if ( ConstrainedDepth == -1 )
  {
    v4 = 2;
    goto LABEL_7;
  }
  v10 = *(_DWORD *)(a1 + 208);
  if ( v10 != -1 && (v10 & 0x10) != 0 && (*(_BYTE *)(v3 + 24) & 2) == 0 )
  {
    v5 = 403;
    v6 = "Forbidden";
LABEL_22:
    v4 = 0;
    goto LABEL_23;
  }
  if ( (unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                       (DAV_BASE_HANDLER *)a1,
                       *(struct IHttpFileInfo **)(a1 + 32)) )
  {
    v11 = HandleDavIfAndLocks(
            *(struct IHttpContext **)(a1 + 8),
            *(struct DAV_LOCK_STORE **)(*(_QWORD *)(a1 + 24) + 3328LL),
            *(const unsigned __int16 **)(a1 + 72),
            (struct LOCK_SET *)(a1 + 568),
            0,
            0,
            0,
            0,
            3u);
    if ( v11 >= 0 )
    {
      XML_RESPONDER::Initialize(
        (XML_RESPONDER *)(a1 + 448),
        *(struct IHttpContext **)(a1 + 8),
        (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL) >> 2) & 1);
      v12 = *(_QWORD *)(a1 + 8);
      *(_DWORD *)(a1 + 440) = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 12LL);
      *(_QWORD *)(a1 + 304) = v12;
      *(_QWORD *)(a1 + 312) = a1 + 432;
      *(_QWORD *)(a1 + 320) = 0;
      *(_QWORD *)(a1 + 336) = -1;
      *(_QWORD *)(a1 + 344) = 0;
      *(_QWORD *)(a1 + 328) = (a1 + 296) & -(__int64)(a1 != 0);
      *(_DWORD *)(a1 + 352) = 0;
      return CAsyncReader::StartRead(a1 + 304);
    }
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v11);
  }
  return 2;
}

```

## disassembly

```asm
0x18000c600  mov     [rsp+arg_0], rbx
0x18000c605  mov     [rsp+arg_8], rbp
0x18000c60a  push    rsi
0x18000c60b  sub     rsp, 50h
0x18000c60f  test    cs:g_dwDebugFlags, 40000000h
0x18000c619  mov     rbx, rcx
0x18000c61c  jz      short loc_18000C624
0x18000c61e  call    cs:__imp_DebugBreak
0x18000c624  mov     rax, [rbx+18h]
0x18000c628  xor     ebp, ebp
0x18000c62a  cmp     [rax+34h], ebp
0x18000c62d  jz      loc_18000C79D
0x18000c633  mov     rsi, [rax+0D00h]
0x18000c63a  cmp     [rsi+1Ch], ebp
0x18000c63d  jz      loc_18000C79D
0x18000c643  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000c647  lea     r8, [rbx+15C8h]; char **
0x18000c64e  lea     rdx, [rbx+230h]; unsigned __int64 *
0x18000c655  call    ?ValidateTimeoutHeader@@YAJPEAVIHttpContext@@PEA_KPEAPEBD@Z; ValidateTimeoutHeader(IHttpContext *,unsigned __int64 *,char const * *)
0x18000c65a  test    eax, eax
0x18000c65c  jns     short loc_18000C673
0x18000c65e  lea     r9d, [rbp+8]
0x18000c662  mov     edx, 190h
0x18000c667  lea     r8, aBadRequest; "Bad Request"
0x18000c66e  jmp     loc_18000C7AC
0x18000c673  mov     eax, [rbx+0D0h]
0x18000c679  cmp     eax, 0FFFFFFFFh
0x18000c67c  jz      short loc_18000C687
0x18000c67e  mov     edx, 1
0x18000c683  test    al, 10h
0x18000c685  jnz     short loc_18000C689
0x18000c687  mov     edx, ebp
0x18000c689  mov     rcx, [rbx+8]
0x18000c68d  call    ?GetConstrainedDepth@@YA?AW4DAV_DEPTH@@PEAVIHttpContext@@H@Z; GetConstrainedDepth(IHttpContext *,int)
0x18000c692  mov     [rbx+228h], eax
0x18000c698  cmp     eax, 0FFFFFFFFh
0x18000c69b  jnz     short loc_18000C6A3
0x18000c69d  lea     r9d, [rax+3]
0x18000c6a1  jmp     short loc_18000C662
0x18000c6a3  mov     eax, [rbx+0D0h]
0x18000c6a9  cmp     eax, 0FFFFFFFFh
0x18000c6ac  jz      short loc_18000C6C9
0x18000c6ae  test    al, 10h
0x18000c6b0  jz      short loc_18000C6C9
0x18000c6b2  test    byte ptr [rsi+18h], 2
0x18000c6b6  jnz     short loc_18000C6C9
0x18000c6b8  mov     edx, 193h
0x18000c6bd  lea     r8, aForbidden; "Forbidden"
0x18000c6c4  jmp     loc_18000C7A9
0x18000c6c9  mov     rdx, [rbx+20h]; struct IHttpFileInfo *
0x18000c6cd  mov     rcx, rbx; this
0x18000c6d0  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x18000c6d5  test    eax, eax
0x18000c6d7  jz      loc_18000C7B8
0x18000c6dd  mov     rdx, [rbx+18h]
0x18000c6e1  lea     r9, [rbx+238h]; struct LOCK_SET *
0x18000c6e8  mov     r8, [rbx+48h]; unsigned __int16 *
0x18000c6ec  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000c6f0  mov     [rsp+58h+var_18], 3; unsigned int
0x18000c6f8  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x18000c6ff  mov     [rsp+58h+var_20], ebp; int
0x18000c703  mov     [rsp+58h+var_28], rbp; struct LOCK_SET *
0x18000c708  mov     [rsp+58h+var_30], rbp; unsigned __int16 *
0x18000c70d  mov     [rsp+58h+var_38], ebp; int
0x18000c711  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x18000c716  test    eax, eax
0x18000c718  jns     short loc_18000C729
0x18000c71a  mov     edx, eax; int
0x18000c71c  mov     rcx, rbx; this
0x18000c71f  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000c724  jmp     loc_18000C7B8
0x18000c729  mov     rax, [rbx+18h]
0x18000c72d  lea     rcx, [rbx+1C0h]; this
0x18000c734  mov     rdx, [rbx+8]; struct IHttpContext *
0x18000c738  mov     r8d, [rax+8]
0x18000c73c  shr     r8d, 2
0x18000c740  and     r8d, 1; int
0x18000c744  call    ?Initialize@XML_RESPONDER@@QEAAXPEAVIHttpContext@@H@Z; XML_RESPONDER::Initialize(IHttpContext *,int)
0x18000c749  mov     rax, [rbx+18h]
0x18000c74d  lea     rdx, [rbx+128h]
0x18000c754  mov     ecx, [rax+0Ch]
0x18000c757  mov     rax, [rbx+8]
0x18000c75b  mov     [rbx+1B8h], ecx
0x18000c761  lea     rcx, [rbx+130h]
0x18000c768  mov     [rcx], rax
0x18000c76b  lea     rax, [rbx+1B0h]
0x18000c772  mov     [rcx+8], rax
0x18000c776  neg     rbx
0x18000c779  mov     [rcx+10h], rbp
0x18000c77d  sbb     rax, rax
0x18000c780  mov     qword ptr [rcx+20h], 0FFFFFFFFFFFFFFFFh
0x18000c788  and     rax, rdx
0x18000c78b  mov     [rcx+28h], rbp
0x18000c78f  mov     [rcx+18h], rax
0x18000c793  mov     [rcx+30h], ebp
0x18000c796  call    ?StartRead@CAsyncReader@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; CAsyncReader::StartRead(void)
0x18000c79b  jmp     short loc_18000C7BD
0x18000c79d  mov     edx, 1F5h; unsigned __int16
0x18000c7a2  lea     r8, aNotImplemented; "Not Implemented"
0x18000c7a9  xor     r9d, r9d; unsigned __int16
0x18000c7ac  mov     rcx, rbx; this
0x18000c7af  mov     [rsp+58h+var_38], ebp; int
0x18000c7b3  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000c7b8  mov     eax, 2
0x18000c7bd  mov     rbx, [rsp+58h+arg_0]
0x18000c7c2  mov     rbp, [rsp+58h+arg_8]
0x18000c7c7  add     rsp, 50h
0x18000c7cb  pop     rsi
0x18000c7cc  retn
```
