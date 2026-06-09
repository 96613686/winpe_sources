# CSession::Init(COleScript *,IActiveScriptSite *)

- ea: `0x180035a58`
- end: `0x180035beb`
- name: `?Init@CSession@@IEAAJPEAVCOleScript@@PEAUIActiveScriptSite@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct COleScript *, struct IActiveScriptSite *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180035710`

## callees

- `0x180035a58`
- `0x18003b8e4`
- `0x180045490`
- `0x180076746`
- `0x180077010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180035b64`
- `KERNEL32!TlsGetValue` at `0x180035b64`
- `KERNEL32!GetCurrentThreadId` at `0x180035ab7`
- `KERNEL32!GetCurrentThreadId` at `0x180035ab7`

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
0x180035a58  push    rbx
0x180035a5a  push    rbp
0x180035a5b  push    rsi
0x180035a5c  push    rdi
0x180035a5d  push    r14
0x180035a5f  sub     rsp, 20h
0x180035a63  test    byte ptr [rdx+370h], 1
0x180035a6a  mov     r14, r8
0x180035a6d  mov     rbp, rdx
0x180035a70  mov     rsi, rcx
0x180035a73  jnz     loc_180035B5E
0x180035a79  mov     ecx, 38h ; '8'; Size
0x180035a7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035a83  mov     rbx, rax
0x180035a86  test    rax, rax
0x180035a89  jz      loc_180035BC2
0x180035a8f  lea     rax, ??_7NameTbl@@6B@; const NameTbl::`vftable'
0x180035a96  mov     [rbx], rax
0x180035a99  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180035aa0  mov     qword ptr [rbx+10h], 0
0x180035aa8  mov     [rbx+18h], rsi
0x180035aac  lock inc dword ptr [rsi+8]
0x180035ab0  mov     dword ptr [rbx+8], 1
0x180035ab7  call    cs:__imp_GetCurrentThreadId
0x180035abd  mov     [rbx+20h], eax
0x180035ac0  lea     rax, ??_7GlobalBinder@@6B@; const GlobalBinder::`vftable'
0x180035ac7  mov     [rbx], rax
0x180035aca  mov     qword ptr [rbx+28h], 0
0x180035ad2  mov     dword ptr [rbx+30h], 0
0x180035ad9  mov     [rsi+40h], rbx
0x180035add  test    rbx, rbx
0x180035ae0  jz      loc_180035B84
0x180035ae6  mov     ecx, 80h; Size
0x180035aeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035af0  mov     rdi, rax
0x180035af3  test    rax, rax
0x180035af6  jz      loc_180035BBE
0x180035afc  xor     edx, edx; Val
0x180035afe  mov     dword ptr [rdi+8], 1
0x180035b05  lea     rax, ??_7VBAErr@@6B@; const VBAErr::`vftable'
0x180035b0c  lea     rcx, [rdi+10h]; void *
0x180035b10  mov     [rdi], rax
0x180035b13  lea     r8d, [rdx+50h]; Size
0x180035b17  call    memset_0
0x180035b1c  mov     qword ptr [rdi+60h], 0
0x180035b24  mov     dword ptr [rdi+68h], 0
0x180035b2b  mov     qword ptr [rdi+70h], 0
0x180035b33  mov     qword ptr [rdi+78h], 0
0x180035b3b  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180035b42  mov     [rsi+0B8h], rdi
0x180035b49  test    rdi, rdi
0x180035b4c  jnz     short loc_180035B8B
0x180035b4e  mov     eax, 800A0007h
0x180035b53  add     rsp, 20h
0x180035b57  pop     r14
0x180035b59  pop     rdi
0x180035b5a  pop     rsi
0x180035b5b  pop     rbp
0x180035b5c  pop     rbx
0x180035b5d  retn
0x180035b5e  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180035b64  call    cs:__imp_TlsGetValue
0x180035b6a  mov     rbx, rax
0x180035b6d  test    rax, rax
0x180035b70  jnz     short loc_180035BC9
0x180035b72  xor     eax, eax
0x180035b74  mov     [rsi+0C8h], rax
0x180035b7b  test    rax, rax
0x180035b7e  jnz     loc_180035A79
0x180035b84  mov     eax, 8007000Eh
0x180035b89  jmp     short loc_180035B53
0x180035b8b  mov     [rsi+20h], rbp
0x180035b8f  lea     r8, [rsi+98h]
0x180035b96  mov     rax, [r14]
0x180035b99  lea     rdx, IID_IActiveScriptSiteInterruptPoll
0x180035ba0  mov     rcx, r14
0x180035ba3  mov     rax, [rax]
0x180035ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bab  test    eax, eax
0x180035bad  jns     short loc_180035BBA
0x180035baf  mov     qword ptr [rsi+98h], 0
0x180035bba  xor     eax, eax
0x180035bbc  jmp     short loc_180035B53
0x180035bbe  xor     edi, edi
0x180035bc0  jmp     short loc_180035B42
0x180035bc2  xor     ebx, ebx
0x180035bc4  jmp     loc_180035AD9
0x180035bc9  mov     ecx, 40h ; '@'; Size
0x180035bce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035bd3  test    rax, rax
0x180035bd6  jz      short loc_180035B72
0x180035bd8  mov     r8d, 1; int
0x180035bde  mov     rdx, rbx; struct ThreadGlobals *
0x180035be1  mov     rcx, rax; this
0x180035be4  call    ??0VarStack@@IEAA@PEAVThreadGlobals@@H@Z; VarStack::VarStack(ThreadGlobals *,int)
0x180035be9  jmp     short loc_180035B74
```
