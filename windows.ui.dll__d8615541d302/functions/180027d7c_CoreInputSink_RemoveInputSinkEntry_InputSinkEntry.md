# CoreInputSink::RemoveInputSinkEntry(_InputSinkEntry *)

- ea: `0x180027d7c`
- end: `0x1800280aa`
- name: `?RemoveInputSinkEntry@CoreInputSink@@AEAAIPEAU_InputSinkEntry@@@Z`
- size: `814`
- prototype: `unsigned int __fastcall(CoreInputSink *__hidden this, struct _InputSinkEntry *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800274f4`
- `0x180029134`

## callees

- `0x1800038e0`
- `0x180027d7c`
- `0x1800280b0`
- `0x180028490`
- `0x180050360`
- `0x180056348`
- `0x180071d6c`
- `0x18008abdc`
- `0x1800ca010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027e6e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027e6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028073`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027e30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027e30`

## string_xrefs

- `0x180027f1a`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\helper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CoreInputSink::RemoveInputSinkEntry(CoreInputSink *this, struct _InputSinkEntry *a2)
{
  _InputSinkEntry *v4; // rdi
  _InputSinkEntry *i; // rsi
  _InputSinkEntry *v6; // r14
  PVOID *v7; // rax
  __int64 v8; // rcx
  void *v9; // rcx
  unsigned int v10; // ebx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // ebx
  DWORD v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rdi
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD CurrentThreadId; // [rsp+20h] [rbp-58h]
  __int64 v21; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v23; // [rsp+90h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, this);
  }
  v4 = 0;
  for ( i = CoreInputSink::_pInputSinkList; i; i = v6 )
  {
    v6 = *(_InputSinkEntry **)i;
    if ( i == a2 )
    {
      --*((_DWORD *)i + 82);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v14 = *((_DWORD *)a2 + 82);
        v15 = GetCurrentThreadId();
        LODWORD(v21) = v14;
        WPP_SF_qDqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
          this,
          v15,
          a2,
          v21);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !*((_DWORD *)i + 82) )
      {
        if ( v4 )
        {
          *(_QWORD *)v4 = *(_QWORD *)i;
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        else
        {
          CoreInputSink::_pInputSinkList = *(_InputSinkEntry **)i;
        }
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 4u )
        {
          v16 = *((_QWORD *)i + 40);
          v17 = *((_QWORD *)i + 39);
          v18 = GetCurrentThreadId();
          WPP_SF_qDqq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
            this,
            v18,
            v17,
            v16);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( *((_QWORD *)i + 40) )
        {
          v23 = 0;
          v12 = Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>::As<Windows::UI::Composition::Internal::IVisualInternal>(
                  (char *)i + 320,
                  &v23);
          if ( v12 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x31D,
              (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\helper.cpp",
              (const char *)(unsigned int)v12,
              CurrentThreadId);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 80LL))(v23, 0);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)i + 320);
          v13 = v23;
          if ( v23 )
          {
            v23 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v8 = *((_QWORD *)i + 39);
        if ( v8 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 280LL))(v8, 0);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)i + 312);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v9 = (void *)*((_QWORD *)i + 1);
        if ( v9 )
        {
          CloseHandle(v9);
          *((_QWORD *)i + 1) = 0;
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v10 = --CoreInputSink::_cInputSinks;
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 4u )
        {
          v19 = GetCurrentThreadId();
          LODWORD(v21) = v10;
          WPP_SF_qDqd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
            this,
            v19,
            i,
            v21);
        }
        _InputSinkEntry::~_InputSinkEntry(i);
        operator delete(i);
        return CoreInputSink::_cInputSinks;
      }
    }
    v4 = i;
  }
  return CoreInputSink::_cInputSinks;
}

```

## disassembly

```asm
0x180027d7c  push    rbx
0x180027d7e  push    rbp
0x180027d7f  push    rsi
0x180027d80  push    rdi
0x180027d81  push    r14
0x180027d83  push    r15
0x180027d85  sub     rsp, 48h
0x180027d89  mov     rbp, rdx
0x180027d8c  mov     r15, rcx
0x180027d8f  lea     rdx, WPP_GLOBAL_Control
0x180027d96  mov     rax, cs:WPP_GLOBAL_Control
0x180027d9d  cmp     rax, rdx
0x180027da0  jnz     loc_180027F2C
0x180027da6  xor     edi, edi
0x180027da8  mov     rsi, cs:?_pInputSinkList@CoreInputSink@@0PEAU_InputSinkEntry@@EA; _InputSinkEntry * CoreInputSink::_pInputSinkList
0x180027daf  test    rsi, rsi
0x180027db2  jz      loc_180027E74
0x180027db8  mov     r14, [rsi]
0x180027dbb  cmp     rsi, rbp
0x180027dbe  jnz     loc_180027F0C
0x180027dc4  dec     dword ptr [rsi+148h]
0x180027dca  mov     rax, cs:WPP_GLOBAL_Control
0x180027dd1  cmp     rax, rdx
0x180027dd4  jnz     loc_180027F7A
0x180027dda  cmp     dword ptr [rsi+148h], 0
0x180027de1  jnz     loc_180027F0C
0x180027de7  mov     rcx, [rsi]
0x180027dea  test    rdi, rdi
0x180027ded  jnz     loc_180027E87
0x180027df3  mov     cs:?_pInputSinkList@CoreInputSink@@0PEAU_InputSinkEntry@@EA, rcx; _InputSinkEntry * CoreInputSink::_pInputSinkList
0x180027dfa  cmp     rax, rdx
0x180027dfd  jnz     loc_180027FD9
0x180027e03  lea     rbx, [rsi+140h]
0x180027e0a  cmp     qword ptr [rbx], 0
0x180027e0e  jnz     loc_180027E96
0x180027e14  lea     rbx, [rsi+138h]
0x180027e1b  mov     rcx, [rbx]
0x180027e1e  test    rcx, rcx
0x180027e21  jnz     loc_18002803A
0x180027e27  mov     rcx, [rsi+8]; hObject
0x180027e2b  test    rcx, rcx
0x180027e2e  jz      short loc_180027E45
0x180027e30  call    cs:__imp_CloseHandle
0x180027e36  mov     qword ptr [rsi+8], 0
0x180027e3e  mov     rax, cs:WPP_GLOBAL_Control
0x180027e45  mov     ebx, cs:?_cInputSinks@CoreInputSink@@0IA; uint CoreInputSink::_cInputSinks
0x180027e4b  dec     ebx
0x180027e4d  mov     cs:?_cInputSinks@CoreInputSink@@0IA, ebx; uint CoreInputSink::_cInputSinks
0x180027e53  lea     rcx, WPP_GLOBAL_Control
0x180027e5a  cmp     rax, rcx
0x180027e5d  jnz     loc_18002805F
0x180027e63  mov     rcx, rsi; this
0x180027e66  call    ??1_InputSinkEntry@@QEAA@XZ; _InputSinkEntry::~_InputSinkEntry(void)
0x180027e6b  mov     rcx, rsi
0x180027e6e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027e74  mov     eax, cs:?_cInputSinks@CoreInputSink@@0IA; uint CoreInputSink::_cInputSinks
0x180027e7a  add     rsp, 48h
0x180027e7e  pop     r15
0x180027e80  pop     r14
0x180027e82  pop     rdi
0x180027e83  pop     rsi
0x180027e84  pop     rbp
0x180027e85  pop     rbx
0x180027e86  retn
0x180027e87  mov     [rdi], rcx
0x180027e8a  mov     rax, cs:WPP_GLOBAL_Control
0x180027e91  jmp     loc_180027DFA
0x180027e96  mov     [rsp+78h+arg_10], 0
0x180027ea2  lea     rdx, [rsp+78h+arg_10]
0x180027eaa  mov     rcx, rbx
0x180027ead  call    ??$As@UIVisualInternal@Internal@Composition@UI@Windows@@@?$ComPtr@UIVisual@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVisualInternal@Internal@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>::As<Windows::UI::Composition::Internal::IVisualInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Internal::IVisualInternal>>)
0x180027eb2  mov     rcx, [rsp+78h]; this
0x180027eb7  test    eax, eax
0x180027eb9  js      short loc_180027F17
0x180027ebb  mov     rcx, [rsp+78h+arg_10]
0x180027ec3  mov     rax, [rcx]
0x180027ec6  xor     edx, edx
0x180027ec8  mov     rax, [rax+50h]
0x180027ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ed1  mov     rcx, rbx
0x180027ed4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180027ed9  nop
0x180027eda  mov     rcx, [rsp+78h+arg_10]
0x180027ee2  test    rcx, rcx
0x180027ee5  jz      short loc_180027F00
0x180027ee7  mov     [rsp+78h+arg_10], 0
0x180027ef3  mov     rax, [rcx]
0x180027ef6  mov     rax, [rax+10h]
0x180027efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eff  nop
0x180027f00  mov     rax, cs:WPP_GLOBAL_Control
0x180027f07  jmp     loc_180027E14
0x180027f0c  mov     rdi, rsi
0x180027f0f  mov     rsi, r14
0x180027f12  jmp     loc_180027DAF
0x180027f17  mov     r9d, eax; char *
0x180027f1a  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180027f21  mov     edx, 31Dh; void *
0x180027f26  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180027f2c  test    byte ptr [rax+1Ch], 40h
0x180027f30  jz      loc_180027DA6
0x180027f36  cmp     byte ptr [rax+19h], 4
0x180027f3a  jb      loc_180027DA6
0x180027f40  call    cs:__imp_GetCurrentThreadId
0x180027f46  mov     edx, 20h ; ' '
0x180027f4b  mov     [rsp+78h+var_50], rbp
0x180027f50  mov     [rsp+78h+var_58], eax
0x180027f54  mov     r9, r15
0x180027f57  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180027f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f65  mov     rcx, [rcx+10h]
0x180027f69  call    WPP_SF_qDq
0x180027f6e  lea     rdx, WPP_GLOBAL_Control
0x180027f75  jmp     loc_180027DA6
0x180027f7a  test    byte ptr [rax+1Ch], 40h
0x180027f7e  jz      loc_180027DDA
0x180027f84  cmp     byte ptr [rax+19h], 4
0x180027f88  jb      loc_180027DDA
0x180027f8e  mov     ebx, [rbp+148h]
0x180027f94  call    cs:__imp_GetCurrentThreadId
0x180027f9a  mov     edx, 21h ; '!'
0x180027f9f  mov     dword ptr [rsp+78h+var_48], ebx
0x180027fa3  mov     [rsp+78h+var_50], rbp
0x180027fa8  mov     [rsp+78h+var_58], eax
0x180027fac  mov     r9, r15
0x180027faf  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180027fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fbd  mov     rcx, [rcx+10h]
0x180027fc1  call    WPP_SF_qDqd
0x180027fc6  mov     rax, cs:WPP_GLOBAL_Control
0x180027fcd  lea     rdx, WPP_GLOBAL_Control
0x180027fd4  jmp     loc_180027DDA
0x180027fd9  test    byte ptr [rax+1Ch], 4
0x180027fdd  jz      loc_180027E03
0x180027fe3  cmp     byte ptr [rax+19h], 4
0x180027fe7  jb      loc_180027E03
0x180027fed  mov     rbx, [rsi+140h]
0x180027ff4  mov     rdi, [rsi+138h]
0x180027ffb  call    cs:__imp_GetCurrentThreadId
0x180028001  mov     edx, 22h ; '"'
0x180028006  mov     [rsp+78h+var_48], rbx
0x18002800b  mov     [rsp+78h+var_50], rdi
0x180028010  mov     [rsp+78h+var_58], eax
0x180028014  mov     r9, r15
0x180028017  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x18002801e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028025  mov     rcx, [rcx+10h]
0x180028029  call    WPP_SF_qDqq
0x18002802e  mov     rax, cs:WPP_GLOBAL_Control
0x180028035  jmp     loc_180027E03
0x18002803a  mov     rax, [rcx]
0x18002803d  xor     edx, edx
0x18002803f  mov     rax, [rax+118h]
0x180028046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002804b  mov     rcx, rbx
0x18002804e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180028053  mov     rax, cs:WPP_GLOBAL_Control
0x18002805a  jmp     loc_180027E27
0x18002805f  test    byte ptr [rax+1Ch], 4
0x180028063  jz      loc_180027E63
0x180028069  cmp     byte ptr [rax+19h], 4
0x18002806d  jb      loc_180027E63
0x180028073  call    cs:__imp_GetCurrentThreadId
0x180028079  mov     edx, 23h ; '#'
0x18002807e  mov     dword ptr [rsp+78h+var_48], ebx
0x180028082  mov     [rsp+78h+var_50], rsi
0x180028087  mov     [rsp+78h+var_58], eax
0x18002808b  mov     r9, r15
0x18002808e  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180028095  mov     rcx, cs:WPP_GLOBAL_Control
0x18002809c  mov     rcx, [rcx+10h]
0x1800280a0  call    WPP_SF_qDqd
0x1800280a5  jmp     loc_180027E63
```
