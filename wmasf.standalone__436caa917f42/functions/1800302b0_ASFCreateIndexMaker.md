# ASFCreateIndexMaker

- ea: `0x1800302b0`
- end: `0x18003038a`
- name: `ASFCreateIndexMaker`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001174`
- `0x1800302b0`
- `0x18003cec4`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall ASFCreateIndexMaker(struct IASFLibrary *a1, struct IASFIndexMakerSink *a2, __int64 a3)
{
  CASFBaseIndexMaker *v7; // rax
  CASFBaseIndexMaker *v8; // rdi
  int v9; // esi
  __int64 v10; // rax
  unsigned int v11; // ebx

  if ( !a3 )
    return 2147942487LL;
  v7 = (CASFBaseIndexMaker *)operator new(0x32D8u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  CASFBaseIndexMaker::CASFBaseIndexMaker(v7);
  *((_DWORD *)v8 + 17) = -1;
  *(_QWORD *)v8 = &CASFIndexMaker::`vftable'{for `IASFIndexMaker'};
  *((_QWORD *)v8 + 1) = &CASFBaseIndexMaker::`vftable'{for `IASFReadWriteTracker'};
  *((_DWORD *)v8 + 16) = 1000;
  *((GUID *)v8 + 2) = CLSID_ASFIndexParametersObject;
  *((GUID *)v8 + 3) = CLSID_ASFIndexObject;
  v9 = CASFBaseIndexMaker::Init(v8, a1, a2);
  v10 = *(_QWORD *)v8;
  if ( v9 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CASFBaseIndexMaker *, GUID *, __int64))v10)(v8, &IID_IASFIndexMaker, a3);
    (*(void (__fastcall **)(CASFBaseIndexMaker *))(*(_QWORD *)v8 + 16LL))(v8);
    return v11;
  }
  else
  {
    (*(void (__fastcall **)(CASFBaseIndexMaker *))(v10 + 16))(v8);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1800302b0  push    rbx
0x1800302b2  push    rbp
0x1800302b3  push    rsi
0x1800302b4  push    rdi
0x1800302b5  sub     rsp, 28h
0x1800302b9  mov     rbx, r8
0x1800302bc  mov     rsi, rdx
0x1800302bf  mov     rbp, rcx
0x1800302c2  test    r8, r8
0x1800302c5  jnz     short loc_1800302D1
0x1800302c7  mov     eax, 80070057h
0x1800302cc  jmp     loc_180030381
0x1800302d1  mov     ecx, 32D8h; Size
0x1800302d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800302db  mov     rdi, rax
0x1800302de  test    rax, rax
0x1800302e1  jz      loc_18003037C
0x1800302e7  mov     rcx, rax; this
0x1800302ea  call    ??0CASFBaseIndexMaker@@QEAA@XZ; CASFBaseIndexMaker::CASFBaseIndexMaker(void)
0x1800302ef  lea     r9, ??_7CASFIndexMaker@@6BIASFIndexMaker@@@; const CASFIndexMaker::`vftable'{for `IASFIndexMaker'}
0x1800302f6  mov     dword ptr [rdi+44h], 0FFFFFFFFh
0x1800302fd  mov     [rdi], r9
0x180030300  lea     rax, ??_7CASFBaseIndexMaker@@6BIASFReadWriteTracker@@@; const CASFBaseIndexMaker::`vftable'{for `IASFReadWriteTracker'}
0x180030307  mov     [rdi+8], rax
0x18003030b  mov     r8, rsi
0x18003030e  mov     rax, [r9+18h]
0x180030312  mov     rdx, rbp
0x180030315  mov     dword ptr [rdi+40h], 3E8h
0x18003031c  mov     rcx, rdi
0x18003031f  movups  xmm0, xmmword ptr cs:CLSID_ASFIndexParametersObject.Data1
0x180030326  movdqu  xmmword ptr [rdi+20h], xmm0
0x18003032b  movups  xmm1, xmmword ptr cs:CLSID_ASFIndexObject.Data1
0x180030332  movdqu  xmmword ptr [rdi+30h], xmm1
0x180030337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003033c  mov     esi, eax
0x18003033e  mov     rcx, rdi
0x180030341  mov     rax, [rdi]
0x180030344  test    esi, esi
0x180030346  jns     short loc_180030355
0x180030348  mov     rax, [rax+10h]
0x18003034c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030351  mov     eax, esi
0x180030353  jmp     short loc_180030381
0x180030355  mov     rax, [rax]
0x180030358  lea     rdx, IID_IASFIndexMaker
0x18003035f  mov     r8, rbx
0x180030362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030367  mov     rcx, [rdi]
0x18003036a  mov     ebx, eax
0x18003036c  mov     rax, [rcx+10h]
0x180030370  mov     rcx, rdi
0x180030373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030378  mov     eax, ebx
0x18003037a  jmp     short loc_180030381
0x18003037c  mov     eax, 8007000Eh
0x180030381  add     rsp, 28h
0x180030385  pop     rdi
0x180030386  pop     rsi
0x180030387  pop     rbp
0x180030388  pop     rbx
0x180030389  retn
```
