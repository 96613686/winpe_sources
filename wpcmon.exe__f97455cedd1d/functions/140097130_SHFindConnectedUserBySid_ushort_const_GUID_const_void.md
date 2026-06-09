# SHFindConnectedUserBySid(ushort const *,_GUID const &,void * *)

- ea: `0x140097130`
- end: `0x140097221`
- name: `?SHFindConnectedUserBySid@@YAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `241`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14008f5a4`

## callees

- `0x140004893`
- `0x140006536`
- `0x140097130`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1400971b0`
- `ADVAPI32!GetLengthSid` at `0x1400971b0`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140097155`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140097155`

## pseudocode

```c
__int64 __fastcall SHFindConnectedUserBySid(const unsigned __int16 *a1, struct _GUID *a2, void **a3)
{
  HRESULT v4; // ebx
  __int64 (__fastcall *v5)(LPVOID, PSID, _QWORD, __int64 *); // rbx
  DWORD LengthSid; // eax
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF
  PSID Sid; // [rsp+60h] [rbp+30h] BYREF
  __int64 v10; // [rsp+68h] [rbp+38h] BYREF

  ppv = a2;
  *a3 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    ppv = 0;
    v4 = CoCreateInstance_0(
           &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
           0,
           1u,
           &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
           &ppv);
    if ( v4 >= 0 )
    {
      v10 = 0;
      v5 = *(__int64 (__fastcall **)(LPVOID, PSID, _QWORD, __int64 *))(*(_QWORD *)ppv + 56LL);
      LengthSid = GetLengthSid(Sid);
      v4 = v5(ppv, Sid, LengthSid, &v10);
      if ( v4 >= 0 )
      {
        v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v10)(
               v10,
               &GUID_9d5f2149_de8c_45f2_b313_6587a04f771d,
               a3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    LocalFree_0(Sid);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140097130  mov     [rsp-18h+arg_8], rdx
0x140097135  push    rbp
0x140097136  push    rbx
0x140097137  push    rdi
0x140097138  mov     rbp, rsp
0x14009713b  sub     rsp, 30h
0x14009713f  lea     rdx, [rbp+Sid]; Sid
0x140097143  mov     qword ptr [r8], 0
0x14009714a  mov     rdi, r8
0x14009714d  mov     [rbp+Sid], 0
0x140097155  call    cs:__imp_ConvertStringSidToSidW
0x14009715b  test    eax, eax
0x14009715d  jnz     short loc_140097169
0x14009715f  mov     ebx, 80004005h
0x140097164  jmp     loc_140097217
0x140097169  xor     edx, edx; pUnkOuter
0x14009716b  mov     [rbp+arg_8], 0
0x140097173  lea     rax, [rbp+arg_8]
0x140097177  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x14009717e  mov     [rsp+30h+ppv], rax; ppv
0x140097183  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x14009718a  lea     r8d, [rdx+1]; dwClsContext
0x14009718e  call    CoCreateInstance_0
0x140097193  mov     ebx, eax
0x140097195  test    eax, eax
0x140097197  js      short loc_14009720E
0x140097199  mov     rax, [rbp+arg_8]
0x14009719d  mov     [rbp+arg_18], 0
0x1400971a5  mov     rcx, [rax]
0x1400971a8  mov     rbx, [rcx+38h]
0x1400971ac  mov     rcx, [rbp+Sid]; pSid
0x1400971b0  call    cs:__imp_GetLengthSid
0x1400971b6  mov     rdx, [rbp+Sid]
0x1400971ba  lea     r9, [rbp+arg_18]
0x1400971be  mov     rcx, [rbp+arg_8]
0x1400971c2  mov     r8d, eax
0x1400971c5  mov     rax, rbx
0x1400971c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400971cd  mov     ebx, eax
0x1400971cf  test    eax, eax
0x1400971d1  js      short loc_1400971FE
0x1400971d3  mov     rcx, [rbp+arg_18]
0x1400971d7  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x1400971de  mov     r8, rdi
0x1400971e1  mov     rax, [rcx]
0x1400971e4  mov     rax, [rax]
0x1400971e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400971ec  mov     rcx, [rbp+arg_18]
0x1400971f0  mov     ebx, eax
0x1400971f2  mov     rax, [rcx]
0x1400971f5  mov     rax, [rax+10h]
0x1400971f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400971fe  mov     rcx, [rbp+arg_8]
0x140097202  mov     rax, [rcx]
0x140097205  mov     rax, [rax+10h]
0x140097209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009720e  mov     rcx, [rbp+Sid]; hMem
0x140097212  call    LocalFree_0
0x140097217  mov     eax, ebx
0x140097219  add     rsp, 30h
0x14009721d  pop     rdi
0x14009721e  pop     rbx
0x14009721f  pop     rbp
0x140097220  retn
```
