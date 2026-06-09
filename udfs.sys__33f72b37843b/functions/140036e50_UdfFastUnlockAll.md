# UdfFastUnlockAll

- ea: `0x140036e50`
- end: `0x14003706a`
- name: `UdfFastUnlockAll`
- size: `538`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PEPROCESS ProcessId)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140036e50`
- `0x140045f10`
- `0x14004ce50`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003704b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c02b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003704b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c02b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140036f93`
- `ntoskrnl!ExAcquireFastMutex` at `0x140036f93`
- `ntoskrnl!ExReleaseFastMutex` at `0x140037023`
- `ntoskrnl!ExReleaseFastMutex` at `0x140037023`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140036f3c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140036fc0`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140036f3c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140036fc0`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140036f64`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140036f64`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140036ebf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140036ebf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037057`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c038`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140037057`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c038`

## pseudocode

```c
char __fastcall UdfFastUnlockAll(PFILE_OBJECT FileObject, PEPROCESS ProcessId, __int64 a3)
{
  __int64 v7; // rdi
  char v8; // bl
  __int64 v9; // r8
  char v10; // r15
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v12; // rcx
  __int64 v13; // rax
  char v14; // al
  __int64 v15; // rax
  __int64 v16; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v17[7]; // [rsp+30h] [rbp-38h] BYREF

  v16 = 0;
  v17[0] = 0;
  *(_QWORD *)(a3 + 8) = 0;
  if ( (unsigned int)UdfDecodeFileObject(FileObject, &v16, v17) != 4 )
  {
    *(_DWORD *)a3 = -1073741811;
    return 1;
  }
  KeEnterCriticalRegion();
  v7 = v16;
  v8 = 1;
  LOBYTE(v9) = 1;
  v10 = UdfAcquireResource(0, *(_QWORD *)(*(_QWORD *)(v16 + 136) + 80LL) + 8LL, v9, 1);
  if ( !v10 || !(unsigned __int8)UdfVerifyScbOperation(0, v7, v17[0]) )
  {
LABEL_20:
    v8 = 0;
    goto LABEL_21;
  }
  if ( *(_QWORD *)(v7 + 504) )
  {
    if ( !*(_QWORD *)(v7 + 88) || FsRtlOplockIsFastIoPossible((POPLOCK)(v7 + 88)) )
    {
      *(_DWORD *)a3 = FsRtlFastUnlockAll(*(PFILE_LOCK *)(v7 + 504), FileObject, ProcessId, 0);
      CurrentThread = KeGetCurrentThread();
      v12 = *(_QWORD *)(v7 + 136);
      if ( CurrentThread != *(struct _KTHREAD **)(v12 + 64) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v12 + 80) + 216LL));
        *(_QWORD *)(*(_QWORD *)(v7 + 136) + 64LL) = CurrentThread;
      }
      ++*(_DWORD *)(*(_QWORD *)(v7 + 136) + 72LL);
      if ( *(_DWORD *)(v7 + 216) || !FsRtlOplockIsFastIoPossible((POPLOCK)(v7 + 88)) )
      {
        v14 = 0;
      }
      else
      {
        v13 = *(_QWORD *)(v7 + 504);
        if ( v13 && *(_BYTE *)(v13 + 16) )
          v14 = 2;
        else
          v14 = 1;
      }
      *(_BYTE *)(v7 + 5) = v14;
      --*(_DWORD *)(*(_QWORD *)(v7 + 136) + 72LL);
      v15 = *(_QWORD *)(v7 + 136);
      if ( !*(_DWORD *)(v15 + 72) )
      {
        *(_QWORD *)(v15 + 64) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v7 + 136) + 80LL) + 216LL));
      }
      goto LABEL_21;
    }
    goto LABEL_20;
  }
  *(_DWORD *)a3 = -1073741698;
LABEL_21:
  if ( v10 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v7 + 136) + 80LL) + 8LL));
  KeLeaveCriticalRegion();
  return v8;
}

```

## disassembly

```asm
0x140036e50  mov     rax, rsp
0x140036e53  mov     [rax+8], rbx
0x140036e57  mov     [rax+10h], rsi
0x140036e5b  push    rdi
0x140036e5c  push    r12
0x140036e5e  push    r13
0x140036e60  push    r14
0x140036e62  push    r15
0x140036e64  sub     rsp, 40h
0x140036e68  mov     rsi, r8
0x140036e6b  mov     r13, rdx
0x140036e6e  mov     r12, rcx
0x140036e71  mov     qword ptr [rax-40h], 0
0x140036e79  mov     qword ptr [rax-38h], 0
0x140036e81  mov     qword ptr [r8+8], 0
0x140036e89  lea     r8, [rax-38h]
0x140036e8d  lea     rdx, [rax-40h]
0x140036e91  call    UdfDecodeFileObject
0x140036e96  cmp     eax, 4
0x140036e99  jz      short loc_140036EBF
0x140036e9b  mov     dword ptr [rsi], 0C000000Dh
0x140036ea1  mov     eax, 1
0x140036ea6  mov     rbx, [rsp+68h+arg_0]
0x140036eab  mov     rsi, [rsp+68h+arg_8]
0x140036eb0  add     rsp, 40h
0x140036eb4  pop     r15
0x140036eb6  pop     r14
0x140036eb8  pop     r13
0x140036eba  pop     r12
0x140036ebc  pop     rdi
0x140036ebd  retn
0x140036ebf  call    cs:__imp_KeEnterCriticalRegion
0x140036ec6  nop     dword ptr [rax+rax+00h]
0x140036ecb  mov     rdi, [rsp+68h+var_40]
0x140036ed0  mov     rax, [rdi+88h]
0x140036ed7  mov     rdx, [rax+50h]
0x140036edb  add     rdx, 8
0x140036edf  mov     ebx, 1
0x140036ee4  mov     r9d, ebx
0x140036ee7  mov     r8b, bl
0x140036eea  xor     ecx, ecx
0x140036eec  call    UdfAcquireResource
0x140036ef1  mov     r15b, al
0x140036ef4  mov     [rsp+68h+arg_10], al
0x140036efb  test    al, al
0x140036efd  jz      loc_140037031
0x140036f03  mov     r8, [rsp+68h+var_38]
0x140036f08  mov     rdx, rdi
0x140036f0b  xor     ecx, ecx
0x140036f0d  call    UdfVerifyScbOperation
0x140036f12  test    al, al
0x140036f14  jz      loc_140037031
0x140036f1a  cmp     qword ptr [rdi+1F8h], 0
0x140036f22  jnz     short loc_140036F2F
0x140036f24  mov     dword ptr [rsi], 0C000007Eh
0x140036f2a  jmp     loc_140037033
0x140036f2f  lea     r14, [rdi+58h]
0x140036f33  cmp     qword ptr [r14], 0
0x140036f37  jz      short loc_140036F50
0x140036f39  mov     rcx, r14; Oplock
0x140036f3c  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140036f43  nop     dword ptr [rax+rax+00h]
0x140036f48  test    al, al
0x140036f4a  jz      loc_140037031
0x140036f50  mov     [rsp+68h+var_48], bl
0x140036f54  xor     r9d, r9d; Context
0x140036f57  mov     r8, r13; ProcessId
0x140036f5a  mov     rdx, r12; FileObject
0x140036f5d  mov     rcx, [rdi+1F8h]; FileLock
0x140036f64  call    cs:__imp_FsRtlFastUnlockAll
0x140036f6b  nop     dword ptr [rax+rax+00h]
0x140036f70  mov     [rsi], eax
0x140036f72  mov     rsi, gs:188h
0x140036f7b  mov     rcx, [rdi+88h]
0x140036f82  cmp     rsi, [rcx+40h]
0x140036f86  jz      short loc_140036FAA
0x140036f88  mov     rcx, [rcx+50h]
0x140036f8c  add     rcx, 0D8h; FastMutex
0x140036f93  call    cs:__imp_ExAcquireFastMutex
0x140036f9a  nop     dword ptr [rax+rax+00h]
0x140036f9f  mov     rax, [rdi+88h]
0x140036fa6  mov     [rax+40h], rsi
0x140036faa  mov     rax, [rdi+88h]
0x140036fb1  add     [rax+48h], ebx
0x140036fb4  cmp     dword ptr [rdi+0D8h], 0
0x140036fbb  jnz     short loc_140036FED
0x140036fbd  mov     rcx, r14; Oplock
0x140036fc0  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140036fc7  nop     dword ptr [rax+rax+00h]
0x140036fcc  test    al, al
0x140036fce  jz      short loc_140036FED
0x140036fd0  mov     rax, [rdi+1F8h]
0x140036fd7  test    rax, rax
0x140036fda  jz      short loc_140036FE9
0x140036fdc  cmp     byte ptr [rax+10h], 0
0x140036fe0  jz      short loc_140036FE9
0x140036fe2  mov     eax, 2
0x140036fe7  jmp     short loc_140036FEF
0x140036fe9  mov     eax, ebx
0x140036feb  jmp     short loc_140036FEF
0x140036fed  xor     eax, eax
0x140036fef  mov     [rdi+5], al
0x140036ff2  mov     rax, [rdi+88h]
0x140036ff9  dec     dword ptr [rax+48h]
0x140036ffc  mov     rax, [rdi+88h]
0x140037003  cmp     dword ptr [rax+48h], 0
0x140037007  jnz     short loc_140037037
0x140037009  mov     qword ptr [rax+40h], 0
0x140037011  mov     rax, [rdi+88h]
0x140037018  mov     rcx, [rax+50h]
0x14003701c  add     rcx, 0D8h; FastMutex
0x140037023  call    cs:__imp_ExReleaseFastMutex
0x14003702a  nop     dword ptr [rax+rax+00h]
0x14003702f  jmp     short loc_140037037
0x140037031  xor     bl, bl
0x140037033  mov     [rsp+68h+var_48], bl
0x140037037  test    r15b, r15b
0x14003703a  jz      short loc_140037057
0x14003703c  mov     rax, [rdi+88h]
0x140037043  mov     rcx, [rax+50h]
0x140037047  add     rcx, 8; Resource
0x14003704b  call    cs:__imp_ExReleaseResourceLite
0x140037052  nop     dword ptr [rax+rax+00h]
0x140037057  call    cs:__imp_KeLeaveCriticalRegion
0x14003705e  nop     dword ptr [rax+rax+00h]
0x140037063  mov     al, bl
0x140037065  jmp     loc_140036EA6
0x14005c006  push    rbp
0x14005c008  sub     rsp, 20h
0x14005c00c  mov     rbp, rdx
0x14005c00f  cmp     byte ptr [rbp+80h], 0
0x14005c016  jz      short loc_14005C038
0x14005c018  mov     rax, [rbp+28h]
0x14005c01c  mov     rcx, [rax+88h]
0x14005c023  mov     rcx, [rcx+50h]
0x14005c027  add     rcx, 8; Resource
0x14005c02b  call    cs:__imp_ExReleaseResourceLite
0x14005c032  nop     dword ptr [rax+rax+00h]
0x14005c037  nop
0x14005c038  call    cs:__imp_KeLeaveCriticalRegion
0x14005c03f  nop     dword ptr [rax+rax+00h]
0x14005c044  nop
0x14005c045  add     rsp, 20h
0x14005c049  pop     rbp
0x14005c04a  retn
```
