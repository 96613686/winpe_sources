# COPY_MOVE_BASE_HANDLER::DoValidatedCopyOrMove(IValidator *,int)

- ea: `0x1800025e4`
- end: `0x18000272d`
- name: `?DoValidatedCopyOrMove@COPY_MOVE_BASE_HANDLER@@QEAAJPEAVIValidator@@H@Z`
- size: `329`
- prototype: `__int64 __fastcall(COPY_MOVE_BASE_HANDLER *__hidden this, struct IValidator *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002fbc`
- `0x18000dfb4`

## callees

- `0x1800025e4`
- `0x18001ac50`
- `0x18001b06c`
- `0x18001b314`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002676`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002676`

## string_xrefs

- `0x1800026c2`: `Impersonation Failure`

## pseudocode

```c
__int64 __fastcall COPY_MOVE_BASE_HANDLER::DoValidatedCopyOrMove(
        COPY_MOVE_BASE_HANDLER *this,
        struct IValidator *a2,
        int a3)
{
  __int64 v3; // rax
  const unsigned __int16 *v7; // rax
  int FileLengthByName; // ebx
  const unsigned __int16 *v9; // rax
  _DWORD *v10; // rax
  int v11; // ebp
  __int64 v12; // rax
  char v14; // [rsp+20h] [rbp-28h]
  unsigned __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD *)a2;
  v15 = 0;
  v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IValidator *))(v3 + 24))(a2);
  FileLengthByName = CopyFileOrDir(*((struct IBaseFileSystem **)this + 30), *((const unsigned __int16 **)this + 23), v7);
  if ( FileLengthByName >= 0 )
  {
    v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IValidator *))(*(_QWORD *)a2 + 24LL))(a2);
    FileLengthByName = GetFileLengthByName(*((struct IBaseFileSystem **)this + 30), v9, &v15);
    if ( FileLengthByName >= 0 )
    {
      v10 = (_DWORD *)*((_QWORD *)this + 51);
      if ( *v10 )
      {
        *v10 = 0;
        RevertToSelf();
      }
      v11 = (*(__int64 (__fastcall **)(struct IValidator *, unsigned __int64))(*(_QWORD *)a2 + 8LL))(a2, v15);
      FileLengthByName = AUTO_IMPERSONATE::Reimpersonate(*((AUTO_IMPERSONATE **)this + 51));
      if ( FileLengthByName >= 0 )
      {
        if ( v11 >= 0 )
        {
          if ( a3 )
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 30) + 104LL))(
              *((_QWORD *)this + 30),
              *((_QWORD *)this + 23));
          FileLengthByName = v11;
        }
        else
        {
          FileLengthByName = -1917904590;
        }
      }
      else
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 272LL))(*((_QWORD *)this + 1));
        v14 = 3;
        (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v12 + 32LL))(
          v12,
          L"Impersonation Failure",
          0,
          (unsigned int)FileLengthByName,
          v14);
      }
    }
  }
  (*(void (__fastcall **)(struct IValidator *))(*(_QWORD *)a2 + 16LL))(a2);
  return (unsigned int)FileLengthByName;
}

```

## disassembly

```asm
0x1800025e4  mov     [rsp+arg_8], rbx
0x1800025e9  mov     [rsp+arg_10], rbp
0x1800025ee  push    rsi
0x1800025ef  push    rdi
0x1800025f0  push    r14
0x1800025f2  sub     rsp, 30h
0x1800025f6  mov     rax, [rdx]
0x1800025f9  mov     rdi, rcx
0x1800025fc  mov     rcx, rdx
0x1800025ff  mov     [rsp+48h+arg_0], 0
0x180002608  mov     r14d, r8d
0x18000260b  mov     rsi, rdx
0x18000260e  mov     rax, [rax+18h]
0x180002612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002617  mov     rdx, [rdi+0B8h]; unsigned __int16 *
0x18000261e  mov     r8, rax; unsigned __int16 *
0x180002621  mov     rcx, [rdi+0F0h]; struct IBaseFileSystem *
0x180002628  call    ?CopyFileOrDir@@YAJPEAVIBaseFileSystem@@PEBG1@Z; CopyFileOrDir(IBaseFileSystem *,ushort const *,ushort const *)
0x18000262d  mov     ebx, eax
0x18000262f  test    eax, eax
0x180002631  js      loc_180002709
0x180002637  mov     rax, [rsi]
0x18000263a  mov     rcx, rsi
0x18000263d  mov     rax, [rax+18h]
0x180002641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002646  mov     rcx, [rdi+0F0h]; struct IBaseFileSystem *
0x18000264d  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x180002652  mov     rdx, rax; unsigned __int16 *
0x180002655  call    ?GetFileLengthByName@@YAJPEAVIBaseFileSystem@@PEBGPEA_K@Z; GetFileLengthByName(IBaseFileSystem *,ushort const *,unsigned __int64 *)
0x18000265a  mov     ebx, eax
0x18000265c  test    eax, eax
0x18000265e  js      loc_180002709
0x180002664  mov     rax, [rdi+198h]
0x18000266b  cmp     dword ptr [rax], 0
0x18000266e  jz      short loc_18000267C
0x180002670  mov     dword ptr [rax], 0
0x180002676  call    cs:__imp_RevertToSelf
0x18000267c  mov     rax, [rsi]
0x18000267f  mov     rcx, rsi
0x180002682  mov     rdx, [rsp+48h+arg_0]
0x180002687  mov     rax, [rax+8]
0x18000268b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002690  mov     rcx, [rdi+198h]; this
0x180002697  mov     ebp, eax
0x180002699  call    ?Reimpersonate@AUTO_IMPERSONATE@@QEAAJXZ; AUTO_IMPERSONATE::Reimpersonate(void)
0x18000269e  mov     ebx, eax
0x1800026a0  test    eax, eax
0x1800026a2  jns     short loc_1800026DD
0x1800026a4  mov     rcx, [rdi+8]
0x1800026a8  mov     rax, [rcx]
0x1800026ab  mov     rax, [rax+110h]
0x1800026b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026b7  mov     r10, rax
0x1800026ba  mov     [rsp+48h+var_28], 3
0x1800026bf  mov     r9d, ebx
0x1800026c2  lea     rdx, aImpersonationF; "Impersonation Failure"
0x1800026c9  xor     r8d, r8d
0x1800026cc  mov     rcx, [rax]
0x1800026cf  mov     rax, [rcx+20h]
0x1800026d3  mov     rcx, r10
0x1800026d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026db  jmp     short loc_180002709
0x1800026dd  test    ebp, ebp
0x1800026df  jns     short loc_1800026E8
0x1800026e1  mov     ebx, 8DAF1932h
0x1800026e6  jmp     short loc_180002709
0x1800026e8  test    r14d, r14d
0x1800026eb  jz      short loc_180002707
0x1800026ed  mov     rcx, [rdi+0F0h]
0x1800026f4  mov     rdx, [rdi+0B8h]
0x1800026fb  mov     rax, [rcx]
0x1800026fe  mov     rax, [rax+68h]
0x180002702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002707  mov     ebx, ebp
0x180002709  mov     rax, [rsi]
0x18000270c  mov     rcx, rsi
0x18000270f  mov     rax, [rax+10h]
0x180002713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002718  mov     rbp, [rsp+48h+arg_10]
0x18000271d  mov     eax, ebx
0x18000271f  mov     rbx, [rsp+48h+arg_8]
0x180002724  add     rsp, 30h
0x180002728  pop     r14
0x18000272a  pop     rdi
0x18000272b  pop     rsi
0x18000272c  retn
```
