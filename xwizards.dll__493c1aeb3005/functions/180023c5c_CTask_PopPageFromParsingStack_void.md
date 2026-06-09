# CTask::PopPageFromParsingStack(void)

- ea: `0x180023c5c`
- end: `0x180023d79`
- name: `?PopPageFromParsingStack@CTask@@AEAAXXZ`
- size: `285`
- prototype: `void __fastcall(CTask *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800200f8`
- `0x180020b3c`
- `0x180021d04`
- `0x1800237d8`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x180023c5c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023d08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023d08`

## pseudocode

```c
void __fastcall CTask::PopPageFromParsingStack(CTask *this)
{
  __int64 v1; // rdi
  unsigned int *v3; // rdi
  __int64 v4; // rcx
  unsigned int LastErrorHRESULT; // eax
  __int64 v6; // rax

  v1 = *((_QWORD *)this + 40);
  if ( *((_QWORD *)this + 39) != v1 )
  {
    v3 = *(unsigned int **)(v1 - 8);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 4) + 16LL))(*((_QWORD *)v3 + 4));
    if ( (v3[12] & 0x2000) != 0 )
      _InterlockedDecrement((volatile signed __int32 *)this + 263);
    if ( (v3[12] & 0x200) != 0 )
      _InterlockedDecrement((volatile signed __int32 *)this + 262);
    v4 = *((_QWORD *)v3 + 5);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v3);
    if ( !HeapFree(*((HANDLE *)this + 50), 0, v3)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
        LastErrorHRESULT);
    }
    v6 = *((_QWORD *)this + 40);
    if ( *((_QWORD *)this + 39) != v6 )
      *((_QWORD *)this + 40) = v6 - 8;
    --*((_DWORD *)this + 97);
  }
}

```

## disassembly

```asm
0x180023c5c  mov     [rsp+arg_0], rbx
0x180023c61  mov     [rsp+arg_8], rsi
0x180023c66  push    rdi
0x180023c67  sub     rsp, 20h
0x180023c6b  mov     rdi, [rcx+140h]
0x180023c72  mov     rbx, rcx
0x180023c75  cmp     [rcx+138h], rdi
0x180023c7c  jz      loc_180023D69
0x180023c82  mov     rdi, [rdi-8]
0x180023c86  mov     rcx, [rdi+20h]
0x180023c8a  mov     rax, [rcx]
0x180023c8d  mov     rax, [rax+10h]
0x180023c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c96  test    dword ptr [rdi+30h], 2000h
0x180023c9d  jz      short loc_180023CA6
0x180023c9f  lock dec dword ptr [rbx+41Ch]
0x180023ca6  test    dword ptr [rdi+30h], 200h
0x180023cad  jz      short loc_180023CB6
0x180023caf  lock dec dword ptr [rbx+418h]
0x180023cb6  mov     rcx, [rdi+28h]
0x180023cba  test    rcx, rcx
0x180023cbd  jz      short loc_180023CCB
0x180023cbf  mov     rax, [rcx]
0x180023cc2  mov     rax, [rax+10h]
0x180023cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cd2  lea     rsi, WPP_GLOBAL_Control
0x180023cd9  cmp     rcx, rsi
0x180023cdc  jz      short loc_180023CFC
0x180023cde  test    byte ptr [rcx+1Ch], 8
0x180023ce2  jz      short loc_180023CFC
0x180023ce4  mov     r9d, [rdi]
0x180023ce7  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180023cee  mov     rcx, [rcx+10h]
0x180023cf2  mov     edx, 20h ; ' '
0x180023cf7  call    WPP_SF_d
0x180023cfc  mov     rcx, [rbx+190h]; hHeap
0x180023d03  mov     r8, rdi; lpMem
0x180023d06  xor     edx, edx; dwFlags
0x180023d08  call    cs:__imp_HeapFree
0x180023d0e  test    eax, eax
0x180023d10  jnz     short loc_180023D48
0x180023d12  mov     rax, cs:WPP_GLOBAL_Control
0x180023d19  cmp     rax, rsi
0x180023d1c  jz      short loc_180023D48
0x180023d1e  test    byte ptr [rax+1Ch], 4
0x180023d22  jz      short loc_180023D48
0x180023d24  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180023d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d30  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180023d37  mov     edx, 21h ; '!'
0x180023d3c  mov     r9d, eax
0x180023d3f  mov     rcx, [rcx+10h]
0x180023d43  call    WPP_SF_d
0x180023d48  mov     rax, [rbx+140h]
0x180023d4f  cmp     [rbx+138h], rax
0x180023d56  jz      short loc_180023D63
0x180023d58  add     rax, 0FFFFFFFFFFFFFFF8h
0x180023d5c  mov     [rbx+140h], rax
0x180023d63  dec     dword ptr [rbx+184h]
0x180023d69  mov     rbx, [rsp+28h+arg_0]
0x180023d6e  mov     rsi, [rsp+28h+arg_8]
0x180023d73  add     rsp, 20h
0x180023d77  pop     rdi
0x180023d78  retn
```
