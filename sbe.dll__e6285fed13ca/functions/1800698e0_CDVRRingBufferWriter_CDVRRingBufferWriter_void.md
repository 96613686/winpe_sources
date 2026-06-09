# CDVRRingBufferWriter::~CDVRRingBufferWriter(void)

- ea: `0x1800698e0`
- end: `0x180069a07`
- name: `??1CDVRRingBufferWriter@@UEAA@XZ`
- size: `295`
- prototype: `void __fastcall(CDVRRingBufferWriter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180069b10`

## callees

- `0x1800017e0`
- `0x18000c1c4`
- `0x180063b90`
- `0x1800698e0`
- `0x180069a10`
- `0x180069a9c`
- `0x18006a3f0`
- `0x180075aec`
- `0x18007b5a0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180069953`
- `KERNEL32!WaitForSingleObject` at `0x180069953`
- `KERNEL32!DeleteCriticalSection` at `0x1800699ce`
- `KERNEL32!DeleteCriticalSection` at `0x1800699ce`
- `ADVAPI32!RegCloseKey` at `0x1800699a6`
- `ADVAPI32!RegCloseKey` at `0x1800699b5`
- `ADVAPI32!RegCloseKey` at `0x1800699a6`
- `ADVAPI32!RegCloseKey` at `0x1800699b5`

## pseudocode

```c
void __fastcall CDVRRingBufferWriter::~CDVRRingBufferWriter(CDVRRingBufferWriter *this, unsigned __int64 a2)
{
  bool v2; // zf
  CAsyncIo *v4; // rcx
  CDVRFileCollection *v5; // rcx
  _QWORD *v6; // rsi
  __int64 v7; // rdx
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  unsigned __int64 v10; // rdx
  HKEY v11; // rcx
  HKEY v12; // rcx

  v2 = (*((_BYTE *)this + 492) & 2) == 0;
  *(_QWORD *)this = &CDVRRingBufferWriter::`vftable'{for `IDVRRingBufferWriter'};
  *((_QWORD *)this + 1) = &CDVRRingBufferWriter::`vftable'{for `IWMStatusCallback'};
  if ( v2 )
    CDVRRingBufferWriter::Close(this);
  v4 = (CAsyncIo *)*((_QWORD *)this + 16);
  if ( v4 )
    CAsyncIo::Release(v4);
  v5 = (CDVRFileCollection *)*((_QWORD *)this + 72);
  if ( v5 )
  {
    CDVRFileCollection::Release(v5, (CDVRRingBufferWriter *)((char *)this + 584));
    *((_QWORD *)this + 72) = 0;
  }
  v6 = (_QWORD *)((char *)this + 456);
  while ( 1 )
  {
    v9 = (_QWORD *)*v6;
    if ( (_QWORD *)*v6 == v6 )
      break;
    WaitForSingleObject((HANDLE)v9[10], 0xFFFFFFFF);
    v7 = *v9;
    if ( *(_QWORD **)(*v9 + 8LL) != v9 || (v8 = (_QWORD *)v9[1], (_QWORD *)*v8 != v9) )
      __fastfail(3u);
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    CDVRRingBufferWriter::ASF_WRITER_NODE::`scalar deleting destructor'(
      (CDVRRingBufferWriter::ASF_WRITER_NODE *)(v9 - 2),
      v7);
  }
  operator delete(*((void **)this + 4), a2);
  operator delete(*((void **)this + 5), v10);
  v11 = (HKEY)*((_QWORD *)this + 9);
  if ( v11 )
    RegCloseKey(v11);
  v12 = (HKEY)*((_QWORD *)this + 10);
  if ( v12 )
    RegCloseKey(v12);
  CPVRIOCounters::Release(*((CPVRIOCounters **)this + 20));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  CDVRFileCollection::CClientInfo::~CClientInfo((CDVRRingBufferWriter *)((char *)this + 584));
  CIndexSampleGenerator::~CIndexSampleGenerator((CDVRRingBufferWriter *)((char *)this + 168));
  *((_QWORD *)this + 11) = &CPVRStreamProf::`vftable';
}

```

## disassembly

```asm
0x1800698e0  push    rbx
0x1800698e2  push    rbp
0x1800698e3  push    rsi
0x1800698e4  push    rdi
0x1800698e5  sub     rsp, 28h
0x1800698e9  test    byte ptr [rcx+1ECh], 2
0x1800698f0  lea     rax, ??_7CDVRRingBufferWriter@@6BIDVRRingBufferWriter@@@; const CDVRRingBufferWriter::`vftable'{for `IDVRRingBufferWriter'}
0x1800698f7  mov     [rcx], rax
0x1800698fa  mov     rbx, rcx
0x1800698fd  lea     rax, ??_7CDVRRingBufferWriter@@6BIWMStatusCallback@@@; const CDVRRingBufferWriter::`vftable'{for `IWMStatusCallback'}
0x180069904  mov     [rcx+8], rax
0x180069908  jnz     short loc_18006990F
0x18006990a  call    ?Close@CDVRRingBufferWriter@@UEAAJXZ; CDVRRingBufferWriter::Close(void)
0x18006990f  mov     rcx, [rbx+80h]; this
0x180069916  test    rcx, rcx
0x180069919  jz      short loc_180069920
0x18006991b  call    ?Release@CAsyncIo@@QEAAJXZ; CAsyncIo::Release(void)
0x180069920  mov     rcx, [rbx+240h]; this
0x180069927  test    rcx, rcx
0x18006992a  jz      short loc_180069943
0x18006992c  lea     rdx, [rbx+248h]; struct CDVRFileCollection::CClientInfo *
0x180069933  call    ?Release@CDVRFileCollection@@QEAAKPEBUCClientInfo@1@@Z; CDVRFileCollection::Release(CDVRFileCollection::CClientInfo const *)
0x180069938  mov     qword ptr [rbx+240h], 0
0x180069943  lea     rsi, [rbx+1C8h]
0x18006994a  jmp     short loc_180069983
0x18006994c  mov     rcx, [rdi+50h]; hHandle
0x180069950  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180069953  call    cs:__imp_WaitForSingleObject
0x180069959  mov     rdx, [rdi]; unsigned int
0x18006995c  cmp     [rdx+8], rdi
0x180069960  jnz     loc_180069A00
0x180069966  mov     rax, [rdi+8]
0x18006996a  cmp     [rax], rdi
0x18006996d  jnz     loc_180069A00
0x180069973  mov     [rax], rdx
0x180069976  lea     rcx, [rdi-10h]; this
0x18006997a  mov     [rdx+8], rax
0x18006997e  call    ??_GASF_WRITER_NODE@CDVRRingBufferWriter@@QEAAPEAXI@Z; CDVRRingBufferWriter::ASF_WRITER_NODE::`scalar deleting destructor'(uint)
0x180069983  mov     rdi, [rsi]
0x180069986  cmp     rdi, rsi
0x180069989  jnz     short loc_18006994C
0x18006998b  mov     rcx, [rbx+20h]; void *
0x18006998f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180069994  mov     rcx, [rbx+28h]; void *
0x180069998  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006999d  mov     rcx, [rbx+48h]; hKey
0x1800699a1  test    rcx, rcx
0x1800699a4  jz      short loc_1800699AC
0x1800699a6  call    cs:__imp_RegCloseKey
0x1800699ac  mov     rcx, [rbx+50h]; hKey
0x1800699b0  test    rcx, rcx
0x1800699b3  jz      short loc_1800699BB
0x1800699b5  call    cs:__imp_RegCloseKey
0x1800699bb  mov     rcx, [rbx+0A0h]; this
0x1800699c2  call    ?Release@CPVRIOCounters@@QEAAJXZ; CPVRIOCounters::Release(void)
0x1800699c7  lea     rcx, [rbx+1F0h]; lpCriticalSection
0x1800699ce  call    cs:__imp_DeleteCriticalSection
0x1800699d4  lea     rcx, [rbx+248h]; this
0x1800699db  call    ??1CClientInfo@CDVRFileCollection@@QEAA@XZ; CDVRFileCollection::CClientInfo::~CClientInfo(void)
0x1800699e0  lea     rcx, [rbx+0A8h]; this
0x1800699e7  call    ??1CIndexSampleGenerator@@UEAA@XZ; CIndexSampleGenerator::~CIndexSampleGenerator(void)
0x1800699ec  lea     rax, ??_7CPVRStreamProf@@6B@; const CPVRStreamProf::`vftable'
0x1800699f3  mov     [rbx+58h], rax
0x1800699f7  add     rsp, 28h
0x1800699fb  pop     rdi
0x1800699fc  pop     rsi
0x1800699fd  pop     rbp
0x1800699fe  pop     rbx
0x1800699ff  retn
0x180069a00  mov     ecx, 3
0x180069a05  int     29h; Win8: RtlFailFast(ecx)
```
