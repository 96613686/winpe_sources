# Threading::ThreadEntered::Initialize(bool)

- ea: `0x140063970`
- end: `0x140063a7f`
- name: `?Initialize@ThreadEntered@Threading@@AEAAX_N@Z`
- size: `271`
- prototype: `void __fastcall(Threading::ThreadEntered *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140062cc0`
- `0x140062ddc`

## callees

- `0x140006338`
- `0x14001f62c`
- `0x1400624c4`
- `0x140062c94`
- `0x140063324`
- `0x140063970`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400639aa`
- `KERNEL32!GetCurrentThreadId` at `0x1400639aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140063992`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140063992`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400639c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400639c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Threading::ThreadEntered::Initialize(Threading::ThreadEntered *this, char a2)
{
  signed __int32 v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[16]; // [rsp+30h] [rbp-68h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v10; // [rsp+60h] [rbp-38h]

  if ( !byte_1401110B8 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids);
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v10 = 0;
    ThreadCancelledException::ThreadCancelledException((ThreadCancelledException *)pExceptionObject);
    throw (ThreadCancelledException *)pExceptionObject;
  }
  if ( !TlsGetValue(dword_140110068) )
  {
    v4 = _InterlockedIncrement(&dword_14010FF08);
    *((_DWORD *)this + 18) = GetCurrentThreadId();
    *((_DWORD *)this + 19) = v4;
    *((_BYTE *)this + 80) = a2;
    TlsSetValue(dword_140110068, (char *)this + 72);
    v5 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, &v7);
    *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,Private::ThreadInfo *,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                             *(_QWORD *)(v6 + 8),
                             (__int64)v8,
                             (_QWORD *)this + 9)
              + 24LL) = (char *)this + 72;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  }
}

```

## disassembly

```asm
0x140063970  push    rbx
0x140063972  push    rbp
0x140063973  push    rsi
0x140063974  push    rdi
0x140063975  sub     rsp, 78h
0x140063979  mov     bpl, dl
0x14006397c  mov     rsi, rcx
0x14006397f  cmp     cs:byte_1401110B8, 0
0x140063986  jz      loc_140063A21
0x14006398c  mov     ecx, cs:dword_140110068; dwTlsIndex
0x140063992  call    cs:__imp_TlsGetValue
0x140063998  test    rax, rax
0x14006399b  jnz     short loc_140063A18
0x14006399d  lea     ebx, [rax+1]
0x1400639a0  lock xadd cs:dword_14010FF08, ebx
0x1400639a8  inc     ebx
0x1400639aa  call    cs:__imp_GetCurrentThreadId
0x1400639b0  lea     rdi, [rsi+48h]
0x1400639b4  mov     [rdi], eax
0x1400639b6  mov     [rdi+4], ebx
0x1400639b9  mov     [rsi+50h], bpl
0x1400639bd  mov     rdx, rdi; lpTlsValue
0x1400639c0  mov     ecx, cs:dword_140110068; dwTlsIndex
0x1400639c6  call    cs:__imp_TlsSetValue
0x1400639cc  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x1400639d1  mov     r8, rax
0x1400639d4  mov     rcx, [rax]
0x1400639d7  mov     rax, [rcx+30h]
0x1400639db  lea     rdx, [rsp+98h+var_78]
0x1400639e0  mov     rcx, r8
0x1400639e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400639e8  nop
0x1400639e9  mov     r8, rdi
0x1400639ec  lea     rdx, [rsp+98h+var_68]
0x1400639f1  mov     rcx, [rax+8]
0x1400639f5  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Umap_traits@_KPEAUThreadInfo@Private@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,Private::ThreadInfo *,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x1400639fa  mov     rcx, [rax]
0x1400639fd  mov     [rcx+18h], rdi
0x140063a01  mov     rcx, [rsp+98h+var_78]
0x140063a06  test    rcx, rcx
0x140063a09  jz      short loc_140063A18
0x140063a0b  mov     rax, [rcx]
0x140063a0e  mov     rax, [rax+18h]
0x140063a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063a17  nop
0x140063a18  add     rsp, 78h
0x140063a1c  pop     rdi
0x140063a1d  pop     rsi
0x140063a1e  pop     rbp
0x140063a1f  pop     rbx
0x140063a20  retn
0x140063a21  lea     rax, WPP_GLOBAL_Control
0x140063a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140063a2f  cmp     rcx, rax
0x140063a32  jz      short loc_140063A4F
0x140063a34  test    byte ptr [rcx+1Ch], 1
0x140063a38  jz      short loc_140063A4F
0x140063a3a  mov     edx, 13h
0x140063a3f  lea     r8, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids
0x140063a46  mov     rcx, [rcx+10h]
0x140063a4a  call    WPP_SF_
0x140063a4f  xorps   xmm0, xmm0
0x140063a52  xor     eax, eax
0x140063a54  movups  [rsp+98h+pExceptionObject], xmm0
0x140063a59  movups  [rsp+98h+var_48], xmm0
0x140063a5e  mov     [rsp+98h+var_38], rax
0x140063a63  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140063a68  call    ??0ThreadCancelledException@@QEAA@XZ; ThreadCancelledException::ThreadCancelledException(void)
0x140063a6d  lea     rdx, _TI4?AVThreadCancelledException@@; pThrowInfo
0x140063a74  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140063a79  call    _CxxThrowException_0
```
