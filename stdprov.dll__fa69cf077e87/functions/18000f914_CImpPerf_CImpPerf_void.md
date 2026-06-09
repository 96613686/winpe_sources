# CImpPerf::CImpPerf(void)

- ea: `0x18000f914`
- end: `0x18000fa5c`
- name: `??0CImpPerf@@QEAA@XZ`
- size: `328`
- prototype: `CImpPerf *__fastcall(CImpPerf *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012680`
- `0x1800126b0`

## callees

- `0x1800013d0`
- `0x180002e10`
- `0x1800042ac`
- `0x18000b6cc`
- `0x18000e91c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fa28`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fa28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fa41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fa41`

## pseudocode

```c
CImpPerf *__fastcall CImpPerf::CImpPerf(CImpPerf *this)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx

  CImpDyn::CImpDyn(this);
  *v2 = &CImpPerf::`vftable'{for `IWbemServices'};
  v2[1] = &CImpPerf::`vftable'{for `IWbemProviderInit'};
  v3 = v2 + 17;
  v2[17] = &CObject::`vftable';
  v2[17] = &PerfCache::`vftable';
  PerfBuff::PerfBuff((PerfBuff *)(v2 + 18));
  PerfBuff::PerfBuff((PerfBuff *)(v3 + 23));
  *((_WORD *)v3 + 188) = 0;
  v3[46] = v3 + 47;
  *((_DWORD *)v3 + 95) = 0;
  v3[45] = -2147483644;
  *((_WORD *)this + 276) = 0;
  *((_QWORD *)this + 68) = (char *)this + 552;
  *((_DWORD *)this + 139) = 0;
  CIndexCache::CIndexCache((CImpPerf *)((char *)this + 592));
  StringCchCopyW((unsigned __int16 *)this + 16, 0x2Au, L"{F00B4404-F8F1-11CE-A5B6-00AA00680C3F}");
  TString::operator=((char *)this + 544, L"local");
  *((_QWORD *)this + 65) = -2147483646;
  *((_DWORD *)this + 132) = 0;
  *((_QWORD *)this + 67) = -2147483644;
  *((_QWORD *)this + 71) = 0;
  *((_DWORD *)this + 144) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 16) = CreateMutexW(0, 0, 0);
  *((_QWORD *)this + 70) = CreateEventW(0, 1, 0, 0);
  return this;
}

```

## disassembly

```asm
0x18000f914  mov     [rsp+arg_10], rbx
0x18000f919  mov     [rsp+arg_0], rcx
0x18000f91e  push    rdi
0x18000f91f  sub     rsp, 20h
0x18000f923  mov     rdi, rcx
0x18000f926  call    ??0CImpDyn@@QEAA@XZ; CImpDyn::CImpDyn(void)
0x18000f92b  nop
0x18000f92c  lea     rax, ??_7CImpPerf@@6BIWbemServices@@@; const CImpPerf::`vftable'{for `IWbemServices'}
0x18000f933  mov     [rcx], rax
0x18000f936  lea     rax, ??_7CImpPerf@@6BIWbemProviderInit@@@; const CImpPerf::`vftable'{for `IWbemProviderInit'}
0x18000f93d  mov     [rcx+8], rax
0x18000f941  lea     rbx, [rcx+88h]
0x18000f948  mov     [rsp+28h+arg_8], rbx
0x18000f94d  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000f954  mov     [rbx], rax
0x18000f957  lea     rax, ??_7PerfCache@@6B@; const PerfCache::`vftable'
0x18000f95e  mov     [rbx], rax
0x18000f961  lea     rcx, [rbx+8]; this
0x18000f965  call    ??0PerfBuff@@QEAA@XZ; PerfBuff::PerfBuff(void)
0x18000f96a  nop
0x18000f96b  lea     rcx, [rbx+0B8h]; this
0x18000f972  call    ??0PerfBuff@@QEAA@XZ; PerfBuff::PerfBuff(void)
0x18000f977  nop
0x18000f978  lea     rcx, [rbx+178h]
0x18000f97f  xor     eax, eax
0x18000f981  mov     [rcx], ax
0x18000f984  mov     [rbx+170h], rcx
0x18000f98b  mov     [rbx+17Ch], eax
0x18000f991  mov     qword ptr [rbx+168h], 0FFFFFFFF80000004h
0x18000f99c  lea     rbx, [rdi+220h]
0x18000f9a3  lea     rdx, [rbx+8]
0x18000f9a7  mov     [rdx], ax
0x18000f9aa  mov     [rbx], rdx
0x18000f9ad  mov     [rbx+0Ch], eax
0x18000f9b0  lea     rcx, [rdi+250h]; this
0x18000f9b7  call    ??0CIndexCache@@QEAA@XZ; CIndexCache::CIndexCache(void)
0x18000f9bc  nop
0x18000f9bd  lea     rcx, [rdi+20h]; unsigned __int16 *
0x18000f9c1  lea     r8, aF00b4404F8f111; "{F00B4404-F8F1-11CE-A5B6-00AA00680C3F}"
0x18000f9c8  mov     edx, 2Ah ; '*'; unsigned __int64
0x18000f9cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f9d2  lea     rdx, aLocal_1; "local"
0x18000f9d9  mov     rcx, rbx
0x18000f9dc  call    ??4TString@@QEAAAEAV0@PEAG@Z; TString::operator=(ushort *)
0x18000f9e1  mov     qword ptr [rdi+208h], 0FFFFFFFF80000002h
0x18000f9ec  mov     dword ptr [rdi+210h], 0
0x18000f9f6  mov     qword ptr [rdi+218h], 0FFFFFFFF80000004h
0x18000fa01  mov     qword ptr [rdi+238h], 0
0x18000fa0c  mov     dword ptr [rdi+240h], 0
0x18000fa16  mov     qword ptr [rdi+248h], 0
0x18000fa21  xor     r8d, r8d; lpName
0x18000fa24  xor     edx, edx; bInitialOwner
0x18000fa26  xor     ecx, ecx; lpMutexAttributes
0x18000fa28  call    cs:__imp_CreateMutexW
0x18000fa2e  mov     [rdi+80h], rax
0x18000fa35  xor     r9d, r9d; lpName
0x18000fa38  xor     r8d, r8d; bInitialState
0x18000fa3b  lea     edx, [r9+1]; bManualReset
0x18000fa3f  xor     ecx, ecx; lpEventAttributes
0x18000fa41  call    cs:__imp_CreateEventW
0x18000fa47  mov     [rdi+230h], rax
0x18000fa4e  mov     rax, rdi
0x18000fa51  mov     rbx, [rsp+28h+arg_10]
0x18000fa56  add     rsp, 20h
0x18000fa5a  pop     rdi
0x18000fa5b  retn
```
