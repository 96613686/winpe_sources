# CShareMediaSettingsWriterImpl::QueryInterface(_GUID const &,void * *)

- ea: `0x180014090`
- end: `0x18001411d`
- name: `?QueryInterface@CShareMediaSettingsWriterImpl@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(CShareMediaSettingsWriterImpl *__hidden this, IID *riid, void **ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003860`
- `0x180003888`
- `0x180014090`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x1800140e0`
- `SHLWAPI!__imp_QISearch` at `0x1800140e0`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriterImpl::QueryInterface(
        CShareMediaSettingsWriterImpl *this,
        IID *riid,
        void **ppv)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  v6 = QISearch(this, &stru_180020890, riid, ppv);
  v7 = v6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids, v6);
  return v7;
}

```

## disassembly

```asm
0x180014090  push    rbx
0x180014092  push    rbp
0x180014093  push    rsi
0x180014094  push    rdi
0x180014095  sub     rsp, 28h
0x180014099  mov     rbx, r8
0x18001409c  mov     rdi, rdx
0x18001409f  mov     rsi, rcx
0x1800140a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140a9  lea     rbp, WPP_GLOBAL_Control
0x1800140b0  cmp     rcx, rbp
0x1800140b3  jz      short loc_1800140D0
0x1800140b5  test    byte ptr [rcx+1Ch], 20h
0x1800140b9  jz      short loc_1800140D0
0x1800140bb  mov     rcx, [rcx+10h]
0x1800140bf  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x1800140c6  mov     edx, 0Eh
0x1800140cb  call    WPP_SF_
0x1800140d0  mov     r9, rbx; ppv
0x1800140d3  lea     rdx, stru_180020890; pqit
0x1800140da  mov     r8, rdi; riid
0x1800140dd  mov     rcx, rsi; that
0x1800140e0  call    cs:__imp_QISearch
0x1800140e6  mov     ebx, eax
0x1800140e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140ef  cmp     rcx, rbp
0x1800140f2  jz      short loc_180014112
0x1800140f4  test    byte ptr [rcx+1Ch], 20h
0x1800140f8  jz      short loc_180014112
0x1800140fa  mov     rcx, [rcx+10h]
0x1800140fe  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180014105  mov     edx, 0Fh
0x18001410a  mov     r9d, eax
0x18001410d  call    WPP_SF_d
0x180014112  mov     eax, ebx
0x180014114  add     rsp, 28h
0x180014118  pop     rdi
0x180014119  pop     rsi
0x18001411a  pop     rbp
0x18001411b  pop     rbx
0x18001411c  retn
```
