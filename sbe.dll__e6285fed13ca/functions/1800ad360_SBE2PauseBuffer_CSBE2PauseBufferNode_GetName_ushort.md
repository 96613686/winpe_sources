# SBE2PauseBuffer::CSBE2PauseBufferNode::GetName(ushort * *)

- ea: `0x1800ad360`
- end: `0x1800ad41a`
- name: `?GetName@CSBE2PauseBufferNode@SBE2PauseBuffer@@UEAAJPEAPEAG@Z`
- size: `186`
- prototype: `__int64 __fastcall(SBE2PauseBuffer::CSBE2PauseBufferNode *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180002e68`
- `0x18000624c`
- `0x1800ad360`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800ad409`
- `KERNEL32!LeaveCriticalSection` at `0x1800ad409`
- `KERNEL32!EnterCriticalSection` at `0x1800ad385`
- `KERNEL32!EnterCriticalSection` at `0x1800ad385`
- `ole32!CoTaskMemAlloc` at `0x1800ad3cd`
- `ole32!CoTaskMemAlloc` at `0x1800ad3cd`
- `ole32!CoTaskMemFree` at `0x1800ad3f9`
- `ole32!CoTaskMemFree` at `0x1800ad3f9`

## pseudocode

```c
__int64 __fastcall SBE2PauseBuffer::CSBE2PauseBufferNode::GetName(
        SBE2PauseBuffer::CSBE2PauseBufferNode *this,
        LPVOID *a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  const unsigned __int16 *v6; // rbp
  int v7; // ebx
  SIZE_T v8; // rcx
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v6 = (const unsigned __int16 *)((char *)this + 96);
  v11 = 0;
  v7 = StringCchLengthW((const unsigned __int16 *)this + 48, 0x104u, &v11);
  if ( v7 >= 0 )
  {
    v8 = 2 * v11 + 2;
    v9 = v11 + 1;
    if ( v8 >= v11 + 1 )
    {
      v10 = (unsigned __int16 *)CoTaskMemAlloc(v8);
      *a2 = v10;
      if ( v10 )
      {
        v7 = StringCchCopyW(v10, v9, v6);
        if ( v7 < 0 )
        {
          CoTaskMemFree(*a2);
          *a2 = 0;
        }
      }
      else
      {
        v7 = -2147024882;
      }
    }
    else
    {
      v7 = -2147024809;
    }
  }
  LeaveCriticalSection(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ad360  push    rbx
0x1800ad362  push    rbp
0x1800ad363  push    rsi
0x1800ad364  push    rdi
0x1800ad365  sub     rsp, 28h
0x1800ad369  mov     rdi, rdx
0x1800ad36c  mov     rbx, rcx
0x1800ad36f  test    rdx, rdx
0x1800ad372  jnz     short loc_1800AD37E
0x1800ad374  mov     eax, 80004003h
0x1800ad379  jmp     loc_1800AD411
0x1800ad37e  lea     rsi, [rcx+30h]
0x1800ad382  mov     rcx, rsi; lpCriticalSection
0x1800ad385  call    cs:__imp_EnterCriticalSection
0x1800ad38b  lea     rbp, [rbx+60h]
0x1800ad38f  mov     [rsp+48h+arg_8], 0
0x1800ad398  mov     rcx, rbp; unsigned __int16 *
0x1800ad39b  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x1800ad3a0  mov     edx, 104h; unsigned __int64
0x1800ad3a5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800ad3aa  mov     ebx, eax
0x1800ad3ac  test    eax, eax
0x1800ad3ae  js      short loc_1800AD406
0x1800ad3b0  mov     rax, [rsp+48h+arg_8]
0x1800ad3b5  lea     rcx, ds:2[rax*2]; cb
0x1800ad3bd  lea     rbx, [rax+1]
0x1800ad3c1  cmp     rcx, rbx
0x1800ad3c4  jnb     short loc_1800AD3CD
0x1800ad3c6  mov     ebx, 80070057h
0x1800ad3cb  jmp     short loc_1800AD406
0x1800ad3cd  call    cs:__imp_CoTaskMemAlloc
0x1800ad3d3  mov     [rdi], rax
0x1800ad3d6  test    rax, rax
0x1800ad3d9  jnz     short loc_1800AD3E2
0x1800ad3db  mov     ebx, 8007000Eh
0x1800ad3e0  jmp     short loc_1800AD406
0x1800ad3e2  mov     r8, rbp; unsigned __int16 *
0x1800ad3e5  mov     rdx, rbx; unsigned __int64
0x1800ad3e8  mov     rcx, rax; unsigned __int16 *
0x1800ad3eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad3f0  mov     ebx, eax
0x1800ad3f2  test    eax, eax
0x1800ad3f4  jns     short loc_1800AD406
0x1800ad3f6  mov     rcx, [rdi]; pv
0x1800ad3f9  call    cs:__imp_CoTaskMemFree
0x1800ad3ff  mov     qword ptr [rdi], 0
0x1800ad406  mov     rcx, rsi; lpCriticalSection
0x1800ad409  call    cs:__imp_LeaveCriticalSection
0x1800ad40f  mov     eax, ebx
0x1800ad411  add     rsp, 28h
0x1800ad415  pop     rdi
0x1800ad416  pop     rsi
0x1800ad417  pop     rbp
0x1800ad418  pop     rbx
0x1800ad419  retn
```
