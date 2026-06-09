# SOS_SharedMemory::Create(MemoryClerkInternal *,IMemObj *,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong,wchar_t const *,void *,ulong,bool)

- ea: `0x100554d20`
- end: `0x100554f91`
- name: `?Create@SOS_SharedMemory@@KAPEAV1@PEAVMemoryClerkInternal@@PEAVIMemObj@@PEAU_SECURITY_ATTRIBUTES@@KKKPEB_WPEAXK_N@Z`
- size: `625`
- prototype: `static struct SOS_SharedMemory *(struct MemoryClerkInternal *, struct IMemObj *, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, unsigned int, const wchar_t *, void *, unsigned int, bool)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1005562f0`
- `0x1005563c0`
- `0x100556b80`
- `0x100557230`

## callees

- `0x1004063c0`
- `0x10040a0c0`
- `0x10041ee60`
- `0x1004360f0`
- `0x100554d20`

## import_xrefs

- `KERNEL32!CreateFileMappingNumaW` at `0x100554e70`
- `KERNEL32!CreateFileMappingNumaW` at `0x100554e70`
- `KERNEL32!CloseHandle` at `0x100554f67`
- `KERNEL32!CloseHandle` at `0x100554f67`
- `KERNEL32!GetLastError` at `0x100554e7e`
- `KERNEL32!GetLastError` at `0x100554e7e`

## string_xrefs

- `0x100554f01`: `Sql\DkTemp\sos\src\soshost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct SOS_SharedMemory *__fastcall SOS_SharedMemory::Create(
        struct MemoryClerkInternal *a1,
        struct IMemObj *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        DWORD a4,
        DWORD dwMaximumSizeHigh,
        DWORD a6,
        const wchar_t *lpName,
        HANDLE hFile,
        DWORD nndPreferred,
        bool a10)
{
  BOOL v14; // esi
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdx
  HANDLE FileMappingNumaW; // rdi
  __int64 v21; // rax
  _QWORD *v22; // rbx
  struct SOS_SharedMemory *result; // rax
  int dwMaximumSizeLow; // [rsp+28h] [rbp-A9h]
  int v25; // [rsp+58h] [rbp-79h] BYREF
  __int64 v26; // [rsp+60h] [rbp-71h]
  int v27; // [rsp+68h] [rbp-69h]
  int v28; // [rsp+6Ch] [rbp-65h]
  __int64 v29; // [rsp+70h] [rbp-61h]
  int v30; // [rsp+78h] [rbp-59h] BYREF
  __int64 v31; // [rsp+80h] [rbp-51h]
  __int64 v32; // [rsp+88h] [rbp-49h]
  __int64 v33; // [rsp+90h] [rbp-41h]
  __int64 v34; // [rsp+98h] [rbp-39h]
  bool v35; // [rsp+A8h] [rbp-29h]
  __int64 v36; // [rsp+B8h] [rbp-19h]
  __int64 v37; // [rsp+C0h] [rbp-11h]
  __int64 v38; // [rsp+C8h] [rbp-9h]

  v36 = -2;
  v14 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v25, 1);
  v30 = 536871088;
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
      + (unsigned int)SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  v17 = *(_QWORD *)(v16 + 600);
  if ( v17 )
    v35 = (unsigned int)SOS_Task::PushWait(v17, &v30) == 0;
  v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
      + (unsigned int)SystemThread_TlsOffset;
  v19 = *(_QWORD *)(v18 + 256);
  if ( !v19 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v19 = *(_QWORD *)(v18 + 256);
  }
  v29 = v19;
  v28 = (*(_DWORD *)(v19 + 800) >> 11) & 1;
  if ( v28 || (*(_BYTE *)(v19 + 800) & 4) == 0 )
  {
    v27 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v19 + 608) + 8LL))(*(_QWORD *)(v19 + 608));
  }
  else
  {
    v27 = 0;
  }
  FileMappingNumaW = CreateFileMappingNumaW(hFile, a3, a4, dwMaximumSizeHigh, a6, lpName, nndPreferred);
  if ( FileMappingNumaW )
    v14 = GetLastError() == 183;
  if ( v27 )
  {
    if ( v28 )
      *(_DWORD *)(v29 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v29 + 608) + 16LL))(
        *(_QWORD *)(v29 + 608),
        v29,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v30);
  *(_DWORD *)(v26 + 616) &= ~v25;
  if ( FileMappingNumaW )
  {
    LOBYTE(dwMaximumSizeLow) = 6;
    v21 = (*(__int64 (__fastcall **)(struct IMemObj *, __int64, const char *, __int64, int))(*(_QWORD *)a2 + 80LL))(
            a2,
            40,
            "Sql\\DkTemp\\sos\\src\\soshost.cpp",
            3753,
            dwMaximumSizeLow);
    v22 = (_QWORD *)v21;
    v37 = v21;
    if ( v21 )
    {
      v38 = v21 + 8;
      *(_DWORD *)(v21 + 8) = 0;
      *(_QWORD *)(v21 + 16) = FileMappingNumaW;
      *(_DWORD *)(v21 + 24) = a4;
      *(_BYTE *)(v21 + 28) = a10;
      *(_QWORD *)(v21 + 32) = a1;
      (*(void (__fastcall **)(char *))(*((_QWORD *)a1 + 8) + 40LL))((char *)a1 + 64);
      *v22 = &ISOSHost_SharedMemoryImpl::`vftable';
    }
    else
    {
      v22 = 0;
    }
    if ( v22 )
    {
      result = (struct SOS_SharedMemory *)(v22 + 1);
      *((_DWORD *)v22 + 2) = v14;
      return result;
    }
    CloseHandle(FileMappingNumaW);
  }
  return 0;
}

```

## disassembly

```asm
0x100554d20  mov     rax, rsp
0x100554d23  mov     [rax+10h], rdx
0x100554d27  push    rbp
0x100554d28  push    r12
0x100554d2a  push    r13
0x100554d2c  push    r14
0x100554d2e  push    r15
0x100554d30  lea     rbp, [rax-2Fh]
0x100554d34  sub     rsp, 0D0h
0x100554d3b  mov     [rbp+27h+var_40], 0FFFFFFFFFFFFFFFEh
0x100554d43  mov     [rax+8], rbx
0x100554d47  mov     [rax+18h], rsi
0x100554d4b  mov     [rax+20h], rdi
0x100554d4f  mov     r12d, r9d
0x100554d52  mov     rdi, r8
0x100554d55  mov     r14, rdx
0x100554d58  mov     r15, rcx
0x100554d5b  xor     r13d, r13d
0x100554d5e  mov     esi, r13d
0x100554d61  lea     edx, [r13+1]
0x100554d65  lea     rcx, [rbp+27h+var_A0]
0x100554d69  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100554d6e  nop
0x100554d6f  lea     rax, [rbp+27h+var_90]
0x100554d73  mov     [rsp+0F0h+var_B0], rax
0x100554d78  mov     [rbp+27h+var_80], 200000B0h
0x100554d7f  mov     [rbp+27h+var_78], r13
0x100554d83  mov     [rbp+27h+var_68], r13
0x100554d87  mov     [rbp+27h+var_70], r13
0x100554d8b  mov     [rbp+27h+var_60], r13
0x100554d8f  mov     [rbp+27h+var_50], r13b
0x100554d93  mov     rcx, gs:58h
0x100554d9c  mov     eax, cs:_tls_index
0x100554da2  mov     ebx, cs:SystemThread_TlsOffset
0x100554da8  add     rbx, [rcx+rax*8]
0x100554dac  mov     rcx, [rbx+100h]; void *
0x100554db3  test    rcx, rcx
0x100554db6  jnz     short loc_100554DC4
0x100554db8  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100554dbd  mov     rcx, [rbx+100h]
0x100554dc4  mov     rcx, [rcx+258h]
0x100554dcb  test    rcx, rcx
0x100554dce  jz      short loc_100554DDF
0x100554dd0  lea     rdx, [rbp+27h+var_80]
0x100554dd4  call    ?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100554dd9  test    eax, eax
0x100554ddb  setz    [rbp+27h+var_50]
0x100554ddf  mov     rcx, gs:58h
0x100554de8  mov     eax, cs:_tls_index
0x100554dee  mov     ebx, cs:SystemThread_TlsOffset
0x100554df4  add     rbx, [rcx+rax*8]
0x100554df8  mov     rdx, [rbx+100h]
0x100554dff  test    rdx, rdx
0x100554e02  jnz     short loc_100554E12
0x100554e04  xor     ecx, ecx; void *
0x100554e06  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100554e0b  mov     rdx, [rbx+100h]
0x100554e12  mov     [rbp+27h+var_88], rdx
0x100554e16  mov     eax, [rdx+320h]
0x100554e1c  shr     eax, 0Bh
0x100554e1f  and     eax, 1
0x100554e22  mov     [rbp+27h+var_8C], eax
0x100554e25  jnz     short loc_100554E36
0x100554e27  test    byte ptr [rdx+320h], 4
0x100554e2e  jz      short loc_100554E36
0x100554e30  mov     [rbp+27h+var_90], r13d
0x100554e34  jmp     short loc_100554E4B
0x100554e36  mov     [rbp+27h+var_90], 1
0x100554e3d  mov     rcx, [rdx+260h]
0x100554e44  mov     rax, [rcx]
0x100554e47  call    qword ptr [rax+8]
0x100554e4a  nop
0x100554e4b  mov     eax, [rbp+27h+arg_40]
0x100554e4e  mov     [rsp+0F0h+nndPreferred], eax; nndPreferred
0x100554e52  mov     rax, [rbp+27h+arg_30]
0x100554e56  mov     [rsp+0F0h+lpName], rax; lpName
0x100554e5b  mov     eax, [rbp+27h+arg_28]
0x100554e5e  mov     [rsp+0F0h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x100554e62  mov     r9d, [rbp+27h+dwMaximumSizeHigh]; dwMaximumSizeHigh
0x100554e66  mov     r8d, r12d; flProtect
0x100554e69  mov     rdx, rdi; lpFileMappingAttributes
0x100554e6c  mov     rcx, [rbp+27h+hFile]; hFile
0x100554e70  call    cs:__imp_CreateFileMappingNumaW
0x100554e76  mov     rdi, rax
0x100554e79  test    rax, rax
0x100554e7c  jz      short loc_100554E90
0x100554e7e  call    cs:__imp_GetLastError
0x100554e84  mov     esi, r13d
0x100554e87  cmp     eax, 0B7h
0x100554e8c  setz    sil
0x100554e90  lea     rax, [rbp+27h+var_90]
0x100554e94  mov     [rsp+0F0h+var_B0], rax
0x100554e99  cmp     [rbp+27h+var_90], 0
0x100554e9d  jz      short loc_100554EC9
0x100554e9f  mov     rdx, [rbp+27h+var_88]
0x100554ea3  mov     rcx, [rdx+260h]
0x100554eaa  cmp     [rbp+27h+var_8C], 0
0x100554eae  jz      short loc_100554EBC
0x100554eb0  or      dword ptr [rdx+320h], 800h
0x100554eba  jmp     short loc_100554EC9
0x100554ebc  mov     rax, [rcx]
0x100554ebf  mov     r8d, 1
0x100554ec5  call    qword ptr [rax+10h]
0x100554ec8  nop
0x100554ec9  lea     rcx, [rbp+27h+var_80]; this
0x100554ecd  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x100554ed2  nop
0x100554ed3  mov     ecx, [rbp+27h+var_A0]
0x100554ed6  not     ecx
0x100554ed8  mov     rax, [rbp+27h+var_98]
0x100554edc  and     [rax+268h], ecx
0x100554ee2  test    rdi, rdi
0x100554ee5  jz      loc_100554F6D
0x100554eeb  mov     dword ptr [rsp+0F0h+var_B0], 0EA9h
0x100554ef3  mov     rax, [r14]
0x100554ef6  mov     byte ptr [rsp+0F0h+dwMaximumSizeLow], 6
0x100554efb  mov     r9d, 0EA9h
0x100554f01  lea     r8, aSqlDktempSosSr_17; "Sql\\DkTemp\\sos\\src\\soshost.cpp"
0x100554f08  mov     edx, 28h ; '('
0x100554f0d  mov     rcx, r14
0x100554f10  call    qword ptr [rax+50h]
0x100554f13  mov     rbx, rax
0x100554f16  mov     [rbp+27h+var_38], rax
0x100554f1a  test    rax, rax
0x100554f1d  jz      short loc_100554F54
0x100554f1f  lea     rdx, [rax+8]
0x100554f23  mov     [rbp+27h+var_30], rdx
0x100554f27  mov     [rdx], r13d
0x100554f2a  mov     [rdx+8], rdi
0x100554f2e  mov     [rdx+10h], r12d
0x100554f32  movzx   ecx, [rbp+27h+arg_48]
0x100554f36  mov     [rdx+14h], cl
0x100554f39  mov     [rdx+18h], r15
0x100554f3d  lea     rcx, [r15+40h]
0x100554f41  mov     rax, [rcx]
0x100554f44  call    qword ptr [rax+28h]
0x100554f47  nop
0x100554f48  lea     rax, ??_7ISOSHost_SharedMemoryImpl@@6B@; const ISOSHost_SharedMemoryImpl::`vftable'
0x100554f4f  mov     [rbx], rax
0x100554f52  jmp     short loc_100554F57
0x100554f54  mov     rbx, r13
0x100554f57  test    rbx, rbx
0x100554f5a  jz      short loc_100554F64
0x100554f5c  lea     rax, [rbx+8]
0x100554f60  mov     [rax], esi
0x100554f62  jmp     short loc_100554F70
0x100554f64  mov     rcx, rdi; hObject
0x100554f67  call    cs:__imp_CloseHandle
0x100554f6d  mov     rax, r13
0x100554f70  lea     r11, [rsp+0F0h+var_20]
0x100554f78  mov     rbx, [r11+30h]
0x100554f7c  mov     rsi, [r11+40h]
0x100554f80  mov     rdi, [r11+48h]
0x100554f84  mov     rsp, r11
0x100554f87  pop     r15
0x100554f89  pop     r14
0x100554f8b  pop     r13
0x100554f8d  pop     r12
0x100554f8f  pop     rbp
0x100554f90  retn
```
