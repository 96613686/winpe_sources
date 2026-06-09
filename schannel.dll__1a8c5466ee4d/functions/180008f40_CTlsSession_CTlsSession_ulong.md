# CTlsSession::CTlsSession(ulong)

- ea: `0x180008f40`
- end: `0x180009063`
- name: `??0CTlsSession@@QEAA@K@Z`
- size: `291`
- prototype: `CTlsSession *__fastcall(CTlsSession *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008240`
- `0x180008310`
- `0x180008bc0`

## callees

- `0x180008f40`
- `0x180009070`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009040`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009040`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008f83`
- `ntdll!RtlInitializeResource` at `0x180008fd1`
- `ntdll!RtlInitializeResource` at `0x180008fd1`

## pseudocode

```c
CTlsSession *__fastcall CTlsSession::CTlsSession(CTlsSession *this, int a2)
{
  DWORD *v4; // rdi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+30h] [rbp-18h]

  CSslBasicAllocator::CSslBasicAllocator(this);
  *(_QWORD *)this = &CTlsSession::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = GetTickCount();
  *((_DWORD *)this + 16) = a2;
  v4 = (DWORD *)((char *)this + 68);
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 44) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_BYTE *)this + 204) = 0;
  *((_DWORD *)this + 52) = -2146893042;
  *((_DWORD *)this + 53) = 0;
  *(_QWORD *)((char *)this + 196) = 0;
  RtlInitializeResource((PRTL_RESOURCE)((char *)this + 80));
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 28) = (char *)this + 216;
  *((_QWORD *)this + 27) = (char *)this + 216;
  v6 = 0;
  v7 = 0;
  if ( LsaTable )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int128 *))(LsaTable + 192))(&v6) )
      *v4 = v6;
    else
      *v4 = -1;
    return this;
  }
  else
  {
    *v4 = GetCurrentProcessId();
    return this;
  }
}

```

## disassembly

```asm
0x180008f40  mov     [rsp+arg_8], rbx
0x180008f45  mov     [rsp+arg_18], rsi
0x180008f4a  mov     [rsp+arg_0], rcx
0x180008f4f  push    rdi
0x180008f50  sub     rsp, 40h
0x180008f54  mov     edi, edx
0x180008f56  mov     rbx, rcx
0x180008f59  call    ??0CSslBasicAllocator@@QEAA@XZ; CSslBasicAllocator::CSslBasicAllocator(void)
0x180008f5e  lea     rcx, ??_7CTlsSession@@6B@; const CTlsSession::`vftable'
0x180008f65  mov     [rbx], rcx
0x180008f68  xor     esi, esi
0x180008f6a  mov     [rbx+8], esi
0x180008f6d  mov     [rbx+10h], rsi
0x180008f71  mov     [rbx+18h], esi
0x180008f74  mov     [rbx+20h], rsi
0x180008f78  mov     [rbx+28h], rsi
0x180008f7c  mov     [rbx+30h], rsi
0x180008f80  mov     [rbx+38h], esi
0x180008f83  call    cs:__imp_GetTickCount
0x180008f89  mov     [rbx+3Ch], eax
0x180008f8c  mov     [rbx+40h], edi
0x180008f8f  lea     rdi, [rbx+44h]
0x180008f93  mov     [rsp+48h+arg_10], rdi
0x180008f98  mov     [rdi], esi
0x180008f9a  mov     [rbx+0B0h], esi
0x180008fa0  mov     [rbx+0B8h], rsi
0x180008fa7  mov     [rbx+0C0h], esi
0x180008fad  mov     [rbx+0CCh], sil
0x180008fb4  mov     dword ptr [rbx+0D0h], 8009030Eh
0x180008fbe  mov     [rbx+0D4h], esi
0x180008fc4  xor     eax, eax
0x180008fc6  mov     [rbx+0C4h], rax
0x180008fcd  lea     rcx, [rbx+50h]; Resource
0x180008fd1  call    cs:__imp_RtlInitializeResource
0x180008fd7  mov     [rbx+48h], esi
0x180008fda  jmp     short loc_180008FE9
0x180008fdc  mov     rbx, [rsp+48h+arg_0]
0x180008fe1  mov     [rbx+48h], eax
0x180008fe4  mov     rdi, [rsp+48h+arg_10]
0x180008fe9  lea     rax, [rbx+0D8h]
0x180008ff0  mov     [rax+8], rax
0x180008ff4  mov     [rax], rax
0x180008ff7  xorps   xmm0, xmm0
0x180008ffa  xor     eax, eax
0x180008ffc  movups  [rsp+48h+var_28], xmm0
0x180009001  mov     [rsp+48h+var_18], rax
0x180009006  mov     rax, cs:LsaTable
0x18000900d  test    rax, rax
0x180009010  jz      short loc_180009040
0x180009012  lea     rcx, [rsp+48h+var_28]
0x180009017  mov     rax, [rax+0C0h]
0x18000901e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009023  test    al, al
0x180009025  jz      short loc_18000905B
0x180009027  mov     eax, dword ptr [rsp+48h+var_28]
0x18000902b  mov     [rdi], eax
0x18000902d  mov     rax, rbx
0x180009030  mov     rbx, [rsp+48h+arg_8]
0x180009035  mov     rsi, [rsp+48h+arg_18]
0x18000903a  add     rsp, 40h
0x18000903e  pop     rdi
0x18000903f  retn
0x180009040  call    cs:__imp_GetCurrentProcessId
0x180009046  mov     [rdi], eax
0x180009048  mov     rax, rbx
0x18000904b  mov     rbx, [rsp+48h+arg_8]
0x180009050  mov     rsi, [rsp+48h+arg_18]
0x180009055  add     rsp, 40h
0x180009059  pop     rdi
0x18000905a  retn
0x18000905b  mov     dword ptr [rdi], 0FFFFFFFFh
0x180009061  jmp     short loc_18000902D
```
