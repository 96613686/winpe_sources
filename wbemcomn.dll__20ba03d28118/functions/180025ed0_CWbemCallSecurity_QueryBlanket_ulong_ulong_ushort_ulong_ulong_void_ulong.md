# CWbemCallSecurity::QueryBlanket(ulong *,ulong *,ushort * *,ulong *,ulong *,void * *,ulong *)

- ea: `0x180025ed0`
- end: `0x180025fef`
- name: `?QueryBlanket@CWbemCallSecurity@@UEAAJPEAK0PEAPEAG00PEAPEAX0@Z`
- size: `287`
- prototype: `__int64 __fastcall(CWbemCallSecurity *__hidden this, unsigned int *, unsigned int *, unsigned __int16 **, unsigned int *, unsigned int *, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x180025ed0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025f62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025f62`

## pseudocode

```c
__int64 __fastcall CWbemCallSecurity::QueryBlanket(
        CWbemCallSecurity *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned int *a5,
        unsigned int *a6,
        void **a7)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int16 *v13; // rax
  signed int v14; // eax
  unsigned int v15; // edi

  if ( !*((_DWORD *)this + 6) )
    return 2147500037LL;
  if ( a2 )
    *a2 = *((_DWORD *)this + 8);
  if ( a3 )
    *a3 = *((_DWORD *)this + 9);
  if ( a6 )
    *a6 = *((_DWORD *)this + 7);
  if ( a5 )
    *a5 = *((_DWORD *)this + 10);
  if ( a4 )
  {
    *a4 = 0;
    v10 = *((_QWORD *)this + 6);
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      v12 = v11 + 1;
      v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v11 + 1));
      *a4 = v13;
      if ( !v13 )
        return 2147942414LL;
      v14 = StringCchCopyW(v13, v12, *((const unsigned __int16 **)this + 6));
      v15 = v14;
      if ( v14 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v14);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids, v15);
        }
      }
    }
  }
  if ( a7 )
    *a7 = (void *)*((_QWORD *)this + 7);
  return 0;
}

```

## disassembly

```asm
0x180025ed0  push    rbx
0x180025ed2  push    rbp
0x180025ed3  push    rsi
0x180025ed4  push    rdi
0x180025ed5  sub     rsp, 28h
0x180025ed9  xor     ebp, ebp
0x180025edb  mov     rdi, r9
0x180025ede  mov     rbx, rcx
0x180025ee1  cmp     [rcx+18h], ebp
0x180025ee4  jz      loc_180025FDB
0x180025eea  test    rdx, rdx
0x180025eed  jz      short loc_180025EF4
0x180025eef  mov     eax, [rcx+20h]
0x180025ef2  mov     [rdx], eax
0x180025ef4  test    r8, r8
0x180025ef7  jz      short loc_180025EFF
0x180025ef9  mov     eax, [rcx+24h]
0x180025efc  mov     [r8], eax
0x180025eff  mov     rcx, [rsp+48h+arg_28]
0x180025f04  test    rcx, rcx
0x180025f07  jz      short loc_180025F0E
0x180025f09  mov     eax, [rbx+1Ch]
0x180025f0c  mov     [rcx], eax
0x180025f0e  mov     rcx, [rsp+48h+arg_20]
0x180025f13  test    rcx, rcx
0x180025f16  jz      short loc_180025F1D
0x180025f18  mov     eax, [rbx+28h]
0x180025f1b  mov     [rcx], eax
0x180025f1d  test    rdi, rdi
0x180025f20  jnz     short loc_180025F41
0x180025f22  mov     rcx, [rsp+48h+arg_30]
0x180025f2a  test    rcx, rcx
0x180025f2d  jz      short loc_180025F36
0x180025f2f  mov     rax, [rbx+38h]
0x180025f33  mov     [rcx], rax
0x180025f36  xor     eax, eax
0x180025f38  add     rsp, 28h
0x180025f3c  pop     rdi
0x180025f3d  pop     rsi
0x180025f3e  pop     rbp
0x180025f3f  pop     rbx
0x180025f40  retn
0x180025f41  mov     [r9], rbp
0x180025f44  mov     rcx, [rbx+30h]
0x180025f48  test    rcx, rcx
0x180025f4b  jz      short loc_180025F22
0x180025f4d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025f51  inc     rax
0x180025f54  cmp     [rcx+rax*2], bp
0x180025f58  jnz     short loc_180025F51
0x180025f5a  lea     rsi, [rax+1]
0x180025f5e  lea     rcx, [rsi+rsi]; cb
0x180025f62  call    cs:__imp_CoTaskMemAlloc
0x180025f68  mov     [rdi], rax
0x180025f6b  test    rax, rax
0x180025f6e  jz      short loc_180025FE5
0x180025f70  mov     r8, [rbx+30h]; unsigned __int16 *
0x180025f74  mov     rdx, rsi; unsigned __int64
0x180025f77  mov     rcx, rax; unsigned __int16 *
0x180025f7a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025f7f  mov     edi, eax
0x180025f81  test    eax, eax
0x180025f83  jns     short loc_180025F22
0x180025f85  mov     edx, eax; int
0x180025f87  lea     rcx, qword_18006A9C0; this
0x180025f8e  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f9a  lea     rax, WPP_GLOBAL_Control
0x180025fa1  cmp     rcx, rax
0x180025fa4  jz      loc_180025F22
0x180025faa  test    byte ptr [rcx+1Ch], 1
0x180025fae  jz      loc_180025F22
0x180025fb4  cmp     byte ptr [rcx+19h], 2
0x180025fb8  jb      loc_180025F22
0x180025fbe  mov     rcx, [rcx+10h]
0x180025fc2  lea     r8, WPP_b9e966f598bb3ae9dbe33aa859f4cbf6_Traceguids
0x180025fc9  mov     edx, 0Fh
0x180025fce  mov     r9d, edi
0x180025fd1  call    WPP_SF_D
0x180025fd6  jmp     loc_180025F22
0x180025fdb  mov     eax, 80004005h
0x180025fe0  jmp     loc_180025F38
0x180025fe5  mov     eax, 8007000Eh
0x180025fea  jmp     loc_180025F38
```
