# CSession::Init(COleScript *,IActiveScriptSite *)

- ea: `0x180036fd8`
- end: `0x18003717b`
- name: `?Init@CSession@@IEAAJPEAVCOleScript@@PEAUIActiveScriptSite@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct COleScript *, struct IActiveScriptSite *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180036c6c`

## callees

- `0x180036fd8`
- `0x18003d040`
- `0x180046884`
- `0x180079436`
- `0x18007a010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800370eb`
- `KERNEL32!TlsGetValue` at `0x1800370eb`
- `KERNEL32!GetCurrentThreadId` at `0x180037037`
- `KERNEL32!GetCurrentThreadId` at `0x180037037`

## pseudocode

```c
__int64 __fastcall CSession::Init(CSession *this, struct COleScript *a2, struct IActiveScriptSite *a3)
{
  _QWORD *v6; // rbx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  struct ThreadGlobals *Value; // rbx
  VarStack *v11; // rax
  VarStack *v12; // rax

  if ( (*((_BYTE *)a2 + 880) & 1) != 0 )
  {
    Value = (struct ThreadGlobals *)TlsGetValue(g_luTls);
    if ( Value && (v12 = (VarStack *)operator new(0x40u)) != 0 )
      v11 = VarStack::VarStack(v12, Value, 1);
    else
      v11 = 0;
    *((_QWORD *)this + 25) = v11;
    if ( !v11 )
      return 2147942414LL;
  }
  v6 = operator new(0x38u);
  if ( v6 )
  {
    *v6 = &NameTbl::`vftable';
    _InterlockedIncrement(&g_cLibRef);
    v6[2] = 0;
    v6[3] = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 8) = GetCurrentThreadId();
    *v6 = &GlobalBinder::`vftable';
    v6[5] = 0;
    *((_DWORD *)v6 + 12) = 0;
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 8) = v6;
  if ( !v6 )
    return 2147942414LL;
  v7 = operator new(0x80u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 1;
    *(_QWORD *)v7 = &VBAErr::`vftable';
    memset_0(v7 + 4, 0, 0x50u);
    *((_QWORD *)v8 + 12) = 0;
    v8[26] = 0;
    *((_QWORD *)v8 + 14) = 0;
    *((_QWORD *)v8 + 15) = 0;
    _InterlockedIncrement(&g_cLibRef);
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 23) = v8;
  if ( !v8 )
    return 2148139015LL;
  *((_QWORD *)this + 4) = a2;
  if ( ((__int64 (__fastcall *)(struct IActiveScriptSite *, GUID *, char *))a3->lpVtbl->QueryInterface)(
         a3,
         &IID_IActiveScriptSiteInterruptPoll,
         (char *)this + 152) < 0 )
    *((_QWORD *)this + 19) = 0;
  return 0;
}

```

## disassembly

```asm
0x180036fd8  push    rbx
0x180036fda  push    rbp
0x180036fdb  push    rsi
0x180036fdc  push    rdi
0x180036fdd  push    r14
0x180036fdf  sub     rsp, 20h
0x180036fe3  test    byte ptr [rdx+370h], 1
0x180036fea  mov     r14, r8
0x180036fed  mov     rbp, rdx
0x180036ff0  mov     rsi, rcx
0x180036ff3  jnz     loc_1800370E5
0x180036ff9  mov     ecx, 38h ; '8'; Size
0x180036ffe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037003  mov     rbx, rax
0x180037006  test    rax, rax
0x180037009  jz      loc_180037152
0x18003700f  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x180037016  mov     [rbx], rax
0x180037019  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180037020  mov     qword ptr [rbx+10h], 0
0x180037028  mov     [rbx+18h], rsi
0x18003702c  lock inc dword ptr [rsi+8]
0x180037030  mov     dword ptr [rbx+8], 1
0x180037037  call    cs:__imp_GetCurrentThreadId
0x18003703e  nop     dword ptr [rax+rax+00h]
0x180037043  mov     [rbx+20h], eax
0x180037046  lea     rax, ??_7GlobalBinder@@6B@; const GlobalBinder::`vftable'
0x18003704d  mov     [rbx], rax
0x180037050  mov     qword ptr [rbx+28h], 0
0x180037058  mov     dword ptr [rbx+30h], 0
0x18003705f  mov     [rsi+40h], rbx
0x180037063  test    rbx, rbx
0x180037066  jz      loc_180037111
0x18003706c  mov     ecx, 80h; Size
0x180037071  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037076  mov     rdi, rax
0x180037079  test    rax, rax
0x18003707c  jz      loc_18003714B
0x180037082  xor     edx, edx; Val
0x180037084  mov     dword ptr [rdi+8], 1
0x18003708b  lea     rax, ??_7VBAErr@@6B@; const VBAErr::`vftable'
0x180037092  lea     rcx, [rdi+10h]; void *
0x180037096  mov     [rdi], rax
0x180037099  lea     r8d, [rdx+50h]; Size
0x18003709d  call    memset_0
0x1800370a2  mov     qword ptr [rdi+60h], 0
0x1800370aa  mov     dword ptr [rdi+68h], 0
0x1800370b1  mov     qword ptr [rdi+70h], 0
0x1800370b9  mov     qword ptr [rdi+78h], 0
0x1800370c1  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x1800370c8  mov     [rsi+0B8h], rdi
0x1800370cf  test    rdi, rdi
0x1800370d2  jnz     short loc_180037118
0x1800370d4  mov     eax, 800A0007h
0x1800370d9  add     rsp, 20h
0x1800370dd  pop     r14
0x1800370df  pop     rdi
0x1800370e0  pop     rsi
0x1800370e1  pop     rbp
0x1800370e2  pop     rbx
0x1800370e3  retn
0x1800370e5  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800370eb  call    cs:__imp_TlsGetValue
0x1800370f2  nop     dword ptr [rax+rax+00h]
0x1800370f7  mov     rbx, rax
0x1800370fa  test    rax, rax
0x1800370fd  jnz     short loc_180037159
0x1800370ff  xor     eax, eax
0x180037101  mov     [rsi+0C8h], rax
0x180037108  test    rax, rax
0x18003710b  jnz     loc_180036FF9
0x180037111  mov     eax, 8007000Eh
0x180037116  jmp     short loc_1800370D9
0x180037118  mov     [rsi+20h], rbp
0x18003711c  lea     r8, [rsi+98h]
0x180037123  mov     rax, [r14]
0x180037126  lea     rdx, IID_IActiveScriptSiteInterruptPoll
0x18003712d  mov     rcx, r14
0x180037130  mov     rax, [rax]
0x180037133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037138  test    eax, eax
0x18003713a  jns     short loc_180037147
0x18003713c  mov     qword ptr [rsi+98h], 0
0x180037147  xor     eax, eax
0x180037149  jmp     short loc_1800370D9
0x18003714b  xor     edi, edi
0x18003714d  jmp     loc_1800370C8
0x180037152  xor     ebx, ebx
0x180037154  jmp     loc_18003705F
0x180037159  mov     ecx, 40h ; '@'; Size
0x18003715e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037163  test    rax, rax
0x180037166  jz      short loc_1800370FF
0x180037168  mov     r8d, 1; int
0x18003716e  mov     rdx, rbx; struct ThreadGlobals *
0x180037171  mov     rcx, rax; this
0x180037174  call    ??0VarStack@@IEAA@PEAVThreadGlobals@@H@Z; VarStack::VarStack(ThreadGlobals *,int)
0x180037179  jmp     short loc_180037101
```
