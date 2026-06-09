# CUpdateCleanup::Purge(unsigned __int64,IEmptyVolumeCacheCallBack *)

- ea: `0x180003620`
- end: `0x1800036b4`
- name: `?Purge@CUpdateCleanup@@UEAAJ_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(CUpdateCleanup *this, __int64, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180003620`

## import_xrefs

- `msvcrt!_time64` at `0x18000364e`
- `msvcrt!_time64` at `0x180003684`
- `msvcrt!_time64` at `0x18000364e`
- `msvcrt!_time64` at `0x180003684`
- `DismApi!_DismCleanImage` at `0x18000367a`
- `DismApi!_DismCleanImage` at `0x18000367a`

## pseudocode

```c
__int64 __fastcall CUpdateCleanup::Purge(CUpdateCleanup *this, __int64 a2, struct IEmptyVolumeCacheCallBack *a3)
{
  __int64 result; // rax
  __time64_t v5; // rdi
  int v6; // ebx

  result = 0;
  *((_QWORD *)this + 79) = a3;
  if ( *((_DWORD *)this + 136) )
  {
    *((_DWORD *)this + 145) = 1;
    v5 = _time64(0);
    v6 = _DismCleanImage(*((unsigned int *)this + 156), 1, 0, *((_QWORD *)this + 77), CCleanupBase::OnProgress, this);
    *((_QWORD *)this + 75) = _time64(0) - v5;
    result = 0;
    if ( v6 < 0 )
      result = (unsigned int)v6;
    *((_DWORD *)this + 152) = (unsigned __int16)result;
  }
  return result;
}

```

## disassembly

```asm
0x180003620  mov     [rsp+arg_0], rbx
0x180003625  mov     [rsp+arg_8], rsi
0x18000362a  push    rdi
0x18000362b  sub     rsp, 30h
0x18000362f  xor     eax, eax
0x180003631  mov     [rcx+278h], r8
0x180003638  mov     rsi, rcx
0x18000363b  cmp     [rcx+220h], eax
0x180003641  jbe     short loc_1800036A4
0x180003643  lea     ebx, [rax+1]
0x180003646  mov     [rcx+244h], ebx
0x18000364c  xor     ecx, ecx; Time
0x18000364e  call    cs:__imp__time64
0x180003654  mov     r9, [rsi+268h]
0x18000365b  xor     r8d, r8d
0x18000365e  mov     ecx, [rsi+270h]
0x180003664  mov     rdi, rax
0x180003667  lea     rax, ?OnProgress@CCleanupBase@@SAXIIPEAX@Z; CCleanupBase::OnProgress(uint,uint,void *)
0x18000366e  mov     [rsp+38h+var_10], rsi
0x180003673  mov     edx, ebx
0x180003675  mov     [rsp+38h+var_18], rax
0x18000367a  call    cs:__imp__DismCleanImage
0x180003680  xor     ecx, ecx; Time
0x180003682  mov     ebx, eax
0x180003684  call    cs:__imp__time64
0x18000368a  sub     rax, rdi
0x18000368d  mov     [rsi+258h], rax
0x180003694  xor     eax, eax
0x180003696  test    ebx, ebx
0x180003698  cmovs   eax, ebx
0x18000369b  movzx   ecx, ax
0x18000369e  mov     [rsi+260h], ecx
0x1800036a4  mov     rbx, [rsp+38h+arg_0]
0x1800036a9  mov     rsi, [rsp+38h+arg_8]
0x1800036ae  add     rsp, 30h
0x1800036b2  pop     rdi
0x1800036b3  retn
```
