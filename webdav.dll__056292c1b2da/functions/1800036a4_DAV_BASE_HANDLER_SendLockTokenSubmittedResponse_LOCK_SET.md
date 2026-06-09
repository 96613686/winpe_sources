# DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(LOCK_SET *)

- ea: `0x1800036a4`
- end: `0x180003796`
- name: `?SendLockTokenSubmittedResponse@DAV_BASE_HANDLER@@IEAAJPEAVLOCK_SET@@@Z`
- size: `242`
- prototype: `int(DAV_BASE_HANDLER *__hidden this, struct LOCK_SET *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002740`
- `0x180007960`
- `0x18000dd90`
- `0x18000f070`
- `0x18000f640`

## callees

- `0x180002e60`
- `0x1800036a4`
- `0x180015038`
- `0x180015134`
- `0x180015430`
- `0x180022520`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000376f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000376f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800036d0`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800036d0`

## pseudocode

```c
__int64 __fastcall DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(DAV_BASE_HANDLER *this, struct LOCK_SET *a2)
{
  struct IHttpContext *v4; // rdx
  __int64 v5; // rax
  int v6; // ebx
  int v8; // [rsp+30h] [rbp-39h] BYREF
  __int16 *v9; // [rsp+38h] [rbp-31h]
  const char *v10; // [rsp+40h] [rbp-29h]
  _BYTE v11[56]; // [rsp+48h] [rbp-21h] BYREF
  int v12; // [rsp+80h] [rbp+17h]
  __int64 v13; // [rsp+88h] [rbp+1Fh]
  int v14; // [rsp+90h] [rbp+27h]

  STRA::STRA((STRA *)v11);
  v4 = (struct IHttpContext *)*((_QWORD *)this + 1);
  v9 = &word_1800263B2;
  v12 = 65537;
  v10 = ">";
  v5 = *((_QWORD *)this + 3);
  v8 = 1;
  v13 = 0;
  v14 = 0;
  XML_RESPONDER::Initialize((XML_RESPONDER *)&v8, v4, (*(_DWORD *)(v5 + 8) >> 2) & 1);
  v6 = XML_RESPONDER::BeginXmlCommon((XML_RESPONDER *)&v8, "error", 0x1A7u, "Locked Error", 1u);
  if ( v6 >= 0 )
  {
    v6 = XML_RESPONDER::SendXmlLockTokenSubmitted((XML_RESPONDER *)&v8, a2);
    if ( v6 >= 0 )
      v6 = XML_RESPONDER::FinishXmlErrorResponse((XML_RESPONDER *)&v8);
  }
  STRA::~STRA((STRA *)v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800036a4  mov     [rsp-8+arg_10], rbx
0x1800036a9  push    rbp
0x1800036aa  push    rsi
0x1800036ab  push    rdi
0x1800036ac  lea     rbp, [rsp-47h]
0x1800036b1  sub     rsp, 0B0h
0x1800036b8  mov     rax, cs:__security_cookie
0x1800036bf  xor     rax, rsp
0x1800036c2  mov     [rbp+57h+var_20], rax
0x1800036c6  mov     rbx, rcx
0x1800036c9  mov     rdi, rdx
0x1800036cc  lea     rcx, [rbp+57h+var_78]
0x1800036d0  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800036d6  mov     rdx, [rbx+8]; struct IHttpContext *
0x1800036da  lea     rax, word_1800263B2
0x1800036e1  mov     [rbp+57h+var_88], rax
0x1800036e5  lea     rcx, [rbp+57h+var_90]; this
0x1800036e9  lea     rax, asc_1800263B8; ">"
0x1800036f0  mov     [rbp+57h+var_40], 10001h
0x1800036f7  mov     [rbp+57h+var_80], rax
0x1800036fb  mov     esi, 1
0x180003700  mov     rax, [rbx+18h]
0x180003704  mov     [rbp+57h+var_90], esi
0x180003707  mov     [rbp+57h+var_38], 0
0x18000370f  mov     [rbp+57h+var_30], 0
0x180003716  mov     r8d, [rax+8]
0x18000371a  shr     r8d, 2
0x18000371e  and     r8d, esi; int
0x180003721  call    ?Initialize@XML_RESPONDER@@QEAAXPEAVIHttpContext@@H@Z; XML_RESPONDER::Initialize(IHttpContext *,int)
0x180003726  mov     r8d, 1A7h; unsigned __int16
0x18000372c  mov     [rsp+0C0h+var_A0], si; unsigned __int16
0x180003731  lea     r9, aLockedError; "Locked Error"
0x180003738  lea     rdx, aError; "error"
0x18000373f  lea     rcx, [rbp+57h+var_90]; this
0x180003743  call    ?BeginXmlCommon@XML_RESPONDER@@AEAAJPEBDG0G@Z; XML_RESPONDER::BeginXmlCommon(char const *,ushort,char const *,ushort)
0x180003748  mov     ebx, eax
0x18000374a  test    eax, eax
0x18000374c  js      short loc_18000376B
0x18000374e  mov     rdx, rdi; struct LOCK_SET *
0x180003751  lea     rcx, [rbp+57h+var_90]; this
0x180003755  call    ?SendXmlLockTokenSubmitted@XML_RESPONDER@@QEAAJPEAVLOCK_SET@@@Z; XML_RESPONDER::SendXmlLockTokenSubmitted(LOCK_SET *)
0x18000375a  mov     ebx, eax
0x18000375c  test    eax, eax
0x18000375e  js      short loc_18000376B
0x180003760  lea     rcx, [rbp+57h+var_90]; this
0x180003764  call    ?FinishXmlErrorResponse@XML_RESPONDER@@QEAAJXZ; XML_RESPONDER::FinishXmlErrorResponse(void)
0x180003769  mov     ebx, eax
0x18000376b  lea     rcx, [rbp+57h+var_78]
0x18000376f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003775  mov     eax, ebx
0x180003777  mov     rcx, [rbp+57h+var_20]
0x18000377b  xor     rcx, rsp; StackCookie
0x18000377e  call    __security_check_cookie
0x180003783  mov     rbx, [rsp+0C0h+arg_10]
0x18000378b  add     rsp, 0B0h
0x180003792  pop     rdi
0x180003793  pop     rsi
0x180003794  pop     rbp
0x180003795  retn
```
