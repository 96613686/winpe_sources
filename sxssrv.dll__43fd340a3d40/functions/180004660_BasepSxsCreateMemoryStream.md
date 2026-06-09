# BasepSxsCreateMemoryStream

- ea: `0x180004660`
- end: `0x1800048f4`
- name: `BasepSxsCreateMemoryStream`
- size: `660`
- prototype: `__int64 __fastcall(__int64 SourceProcessHandle, __int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003310`

## callees

- `0x180004660`
- `0x180004900`
- `0x180006654`
- `0x18000666c`
- `0x180008010`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x1800046cd`
- `ntdll!NtDuplicateObject` at `0x1800047ea`
- `ntdll!NtDuplicateObject` at `0x1800046cd`
- `ntdll!NtDuplicateObject` at `0x1800047ea`

## pseudocode

```c
__int64 __fastcall BasepSxsCreateMemoryStream(
        __int64 SourceProcessHandle,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // rbp
  char v8; // al
  HANDLE v9; // rdx
  NTSTATUS v10; // esi
  void *v11; // rdx
  int v12; // ecx
  __int64 (__fastcall **v13)(); // r9
  void *v14; // rax
  char *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  HANDLE v23; // rax
  PVOID BaseAddress; // [rsp+40h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+10h] BYREF
  void *TargetHandle; // [rsp+88h] [rbp+20h] BYREF

  TargetHandle = 0;
  Handle = 0;
  v7 = SourceProcessHandle;
  BaseAddress = 0;
  v8 = *(_BYTE *)(a2 + 2);
  if ( v8 == 2 )
  {
    v9 = (HANDLE)SourceProcessHandle;
    goto LABEL_3;
  }
  v9 = *(HANDLE *)(a2 + 32);
  if ( (unsigned __int8)(v8 - 4) <= 1u )
LABEL_3:
    SourceProcessHandle = -1;
  v10 = NtDuplicateObject((HANDLE)SourceProcessHandle, v9, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0, 0, 2u);
  if ( v10 < 0 )
  {
    TargetHandle = 0;
    goto LABEL_10;
  }
  v11 = *(void **)(a2 + 24);
  if ( !v11
    || ((unsigned __int8)(*(_BYTE *)(a2 + 2) - 4) <= 1u ? (v19 = -1) : (v19 = v7),
        v10 = NtDuplicateObject((HANDLE)v19, v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &Handle, 0, 0, 2u),
        v10 >= 0) )
  {
    v12 = *(unsigned __int8 *)(a2 + 2);
    if ( v12 != 1 )
    {
      v20 = v12 - 2;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( !v21 )
        {
LABEL_28:
          v10 = BasepSxsMapViewOfSection(&BaseAddress, *(_QWORD *)(a2 + 48));
          if ( v10 < 0 )
            goto LABEL_10;
          a3[1] = 0;
          a3[4] = 0;
          v13 = off_180009070;
          a3[6] = 0;
          v15 = (char *)BaseAddress;
          *a3 = off_180009070;
          a3[5] = BaseSxsFinalReleaseMemoryMappedStream;
          v23 = Handle;
          a3[7] = 0;
          a3[3] = v15;
          a3[2] = v15;
          v16 = *(_QWORD *)(a2 + 48);
          a3[7] = v23;
          BaseAddress = 0;
          Handle = 0;
          goto LABEL_8;
        }
        v22 = v21 - 1;
        if ( v22 )
        {
          if ( v22 != 1 )
          {
            v10 = -1073741811;
            goto LABEL_10;
          }
          goto LABEL_28;
        }
      }
    }
    a3[1] = 0;
    a3[2] = 0;
    v13 = off_180009000;
    a3[3] = 0;
    a3[4] = 0;
    a3[5] = RtlFinalReleaseOutOfProcessMemoryStream;
    v14 = TargetHandle;
    *a3 = off_180009000;
    a3[6] = v14;
    v15 = *(char **)(a2 + 40);
    a3[3] = v15;
    a3[2] = v15;
    v16 = *(_QWORD *)(a2 + 48);
    TargetHandle = 0;
LABEL_8:
    v17 = a5;
    a3[4] = &v15[v16];
    v10 = 0;
    if ( ((int (__fastcall *)(_QWORD *, GUID *, __int64))*v13)(a3, &IID_ISequentialStream, v17) < 0 )
      v10 = -1073741637;
  }
LABEL_10:
  if ( Handle )
    NtClose_0(Handle);
  if ( TargetHandle )
    NtClose_0(TargetHandle);
  if ( BaseAddress )
    NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180004660  mov     rax, rsp
0x180004663  mov     [rax+8], rbx
0x180004667  mov     [rax+18h], rbp
0x18000466b  mov     [rax+20h], r9
0x18000466f  push    rsi
0x180004670  push    rdi
0x180004671  push    r14
0x180004673  sub     rsp, 50h
0x180004677  xor     r14d, r14d
0x18000467a  mov     rbx, r8
0x18000467d  mov     [rax+20h], r14
0x180004681  mov     rdi, rdx
0x180004684  mov     [rax+10h], r14
0x180004688  mov     rbp, rcx
0x18000468b  mov     [rax-28h], r14
0x18000468f  movzx   eax, byte ptr [rdx+2]
0x180004693  cmp     al, 2
0x180004695  jz      loc_180004805
0x18000469b  mov     rdx, [rdx+20h]; SourceHandle
0x18000469f  sub     al, 4
0x1800046a1  cmp     al, 1
0x1800046a3  ja      loc_18000480D
0x1800046a9  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800046b0  mov     rcx, r8; SourceProcessHandle
0x1800046b3  mov     [rsp+68h+Options], 2; Options
0x1800046bb  lea     r9, [rsp+68h+TargetHandle]; TargetHandle
0x1800046c3  mov     [rsp+68h+HandleAttributes], r14d; HandleAttributes
0x1800046c8  mov     [rsp+68h+DesiredAccess], r14d; DesiredAccess
0x1800046cd  call    cs:__imp_NtDuplicateObject
0x1800046d4  nop     dword ptr [rax+rax+00h]
0x1800046d9  mov     esi, eax
0x1800046db  test    eax, eax
0x1800046dd  js      loc_1800048BD
0x1800046e3  mov     rdx, [rdi+18h]; SourceHandle
0x1800046e7  test    rdx, rdx
0x1800046ea  jnz     loc_1800047BB
0x1800046f0  movzx   ecx, byte ptr [rdi+2]
0x1800046f4  cmp     ecx, 1
0x1800046f7  jnz     loc_180004819
0x1800046fd  mov     [rbx+8], r14
0x180004701  lea     rax, RtlFinalReleaseOutOfProcessMemoryStream
0x180004708  mov     [rbx+10h], r14
0x18000470c  lea     r9, off_180009000
0x180004713  mov     [rbx+18h], r14
0x180004717  mov     [rbx+20h], r14
0x18000471b  mov     [rbx+28h], rax
0x18000471f  mov     rax, [rsp+68h+TargetHandle]
0x180004727  mov     [rbx], r9
0x18000472a  mov     [rbx+30h], rax
0x18000472e  mov     rcx, [rdi+28h]
0x180004732  mov     [rbx+18h], rcx
0x180004736  mov     [rbx+10h], rcx
0x18000473a  mov     rdx, [rdi+30h]
0x18000473e  mov     [rsp+68h+TargetHandle], r14
0x180004746  mov     r8, [rsp+68h+arg_20]
0x18000474e  add     rdx, rcx
0x180004751  mov     [rbx+20h], rdx
0x180004755  mov     rcx, rbx
0x180004758  mov     rax, [r9]
0x18000475b  lea     rdx, IID_ISequentialStream
0x180004762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004767  test    eax, eax
0x180004769  mov     esi, r14d
0x18000476c  mov     ecx, 0C00000BBh
0x180004771  cmovs   esi, ecx
0x180004774  mov     rcx, [rsp+68h+Handle]; Handle
0x180004779  test    rcx, rcx
0x18000477c  jz      short loc_180004783
0x18000477e  call    NtClose_0
0x180004783  mov     rcx, [rsp+68h+TargetHandle]; Handle
0x18000478b  test    rcx, rcx
0x18000478e  jnz     loc_1800048D9
0x180004794  mov     rdx, [rsp+68h+BaseAddress]; BaseAddress
0x180004799  test    rdx, rdx
0x18000479c  jnz     loc_1800048E3
0x1800047a2  mov     rbx, [rsp+68h+arg_0]
0x1800047a7  mov     eax, esi
0x1800047a9  mov     rbp, [rsp+68h+arg_10]
0x1800047b1  add     rsp, 50h
0x1800047b5  pop     r14
0x1800047b7  pop     rdi
0x1800047b8  pop     rsi
0x1800047b9  retn
0x1800047bb  movzx   eax, byte ptr [rdi+2]
0x1800047bf  lea     r9, [rsp+68h+Handle]; TargetHandle
0x1800047c4  mov     [rsp+68h+Options], 2; Options
0x1800047cc  sub     al, 4
0x1800047ce  mov     [rsp+68h+HandleAttributes], r14d; HandleAttributes
0x1800047d3  mov     [rsp+68h+DesiredAccess], r14d; DesiredAccess
0x1800047d8  cmp     al, 1
0x1800047da  jbe     loc_1800048CA
0x1800047e0  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800047e7  mov     rcx, rbp; SourceProcessHandle
0x1800047ea  call    cs:__imp_NtDuplicateObject
0x1800047f1  nop     dword ptr [rax+rax+00h]
0x1800047f6  mov     esi, eax
0x1800047f8  test    eax, eax
0x1800047fa  jns     loc_1800046F0
0x180004800  jmp     loc_180004774
0x180004805  mov     rdx, rbp
0x180004808  jmp     loc_1800046A9
0x18000480d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004814  jmp     loc_1800046B3
0x180004819  sub     ecx, 2
0x18000481c  jz      loc_1800046FD
0x180004822  sub     ecx, 1
0x180004825  jz      short loc_18000483F
0x180004827  sub     ecx, 1
0x18000482a  jz      loc_1800046FD
0x180004830  cmp     ecx, 1
0x180004833  jz      short loc_18000483F
0x180004835  mov     esi, 0C000000Dh
0x18000483a  jmp     loc_180004774
0x18000483f  mov     rax, [rdi+30h]
0x180004843  lea     rcx, [rsp+68h+BaseAddress]; BaseAddress
0x180004848  mov     r9, [rdi+28h]
0x18000484c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180004853  mov     r8, [rsp+68h+TargetHandle]
0x18000485b  mov     qword ptr [rsp+68h+DesiredAccess], rax; ULONG_PTR
0x180004860  call    BasepSxsMapViewOfSection
0x180004865  mov     esi, eax
0x180004867  test    eax, eax
0x180004869  js      loc_180004774
0x18000486f  mov     [rbx+8], r14
0x180004873  lea     rax, BaseSxsFinalReleaseMemoryMappedStream
0x18000487a  mov     [rbx+20h], r14
0x18000487e  lea     r9, off_180009070
0x180004885  mov     [rbx+30h], r14
0x180004889  mov     rcx, [rsp+68h+BaseAddress]
0x18000488e  mov     [rbx], r9
0x180004891  mov     [rbx+28h], rax
0x180004895  mov     rax, [rsp+68h+Handle]
0x18000489a  mov     [rbx+38h], r14
0x18000489e  mov     [rbx+18h], rcx
0x1800048a2  mov     [rbx+10h], rcx
0x1800048a6  mov     rdx, [rdi+30h]
0x1800048aa  mov     [rbx+38h], rax
0x1800048ae  mov     [rsp+68h+BaseAddress], r14
0x1800048b3  mov     [rsp+68h+Handle], r14
0x1800048b8  jmp     loc_180004746
0x1800048bd  mov     [rsp+68h+TargetHandle], r14
0x1800048c5  jmp     loc_180004774
0x1800048ca  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800048d1  mov     r8, rcx
0x1800048d4  jmp     loc_1800047EA
0x1800048d9  call    NtClose_0
0x1800048de  jmp     loc_180004794
0x1800048e3  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800048ea  call    NtUnmapViewOfSection_0
0x1800048ef  jmp     loc_1800047A2
```
