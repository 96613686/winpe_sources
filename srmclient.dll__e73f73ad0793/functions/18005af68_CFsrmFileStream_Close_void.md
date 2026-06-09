# CFsrmFileStream::Close(void)

- ea: `0x18005af68`
- end: `0x18005b120`
- name: `?Close@CFsrmFileStream@@QEAAXXZ`
- size: `440`
- prototype: `void __fastcall(CFsrmFileStream *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005a774`
- `0x18005b2a8`
- `0x1800a0428`
- `0x1800a10e0`

## callees

- `0x18005af68`
- `0x18005b128`
- `0x18005ca24`
- `0x18006febc`
- `0x1800700b8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005b03f`
- `KERNEL32!CloseHandle` at `0x18005b063`
- `KERNEL32!CloseHandle` at `0x18005b0a9`
- `KERNEL32!CloseHandle` at `0x18005b03f`
- `KERNEL32!CloseHandle` at `0x18005b063`
- `KERNEL32!CloseHandle` at `0x18005b0a9`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x18005b02f`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x18005b02f`
- `KERNEL32!CloseThreadpoolWait` at `0x18005b08c`
- `KERNEL32!CloseThreadpoolWait` at `0x18005b08c`

## string_xrefs

- `0x18005af90`: `base\fs\fsrm\service\stream\streamlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFsrmFileStream::Close(CFsrmFileStream *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  void *v6; // rcx
  int v7; // [rsp+40h] [rbp-178h] BYREF
  _QWORD *v8; // [rsp+48h] [rbp-170h]
  _com_error *v9; // [rsp+50h] [rbp-168h] BYREF
  const exception *v10; // [rsp+58h] [rbp-160h] BYREF
  _QWORD v11[3]; // [rsp+60h] [rbp-158h] BYREF
  int v12; // [rsp+78h] [rbp-140h]
  int v13; // [rsp+7Ch] [rbp-13Ch]
  int v14; // [rsp+80h] [rbp-138h]
  _BYTE v15[96]; // [rsp+88h] [rbp-130h] BYREF
  int v16; // [rsp+E8h] [rbp-D0h]
  _QWORD v17[5]; // [rsp+F0h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+11Ch] [rbp-9Ch]

  v8 = v11;
  v11[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v11[1] = L"CFsrmFileStream::Close";
  v11[2] = L"STREAMLC";
  v12 = 668;
  v13 = 17;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v17, (const struct CSrmDebugInfo *)v11, 0);
  if ( *((_BYTE *)this + 96) )
  {
    try
    {
      v2 = (struct _TP_WAIT *)*((_QWORD *)this + 19);
      if ( v2 )
        WaitForThreadpoolWaitCallbacks(v2, 1);
      v3 = (void *)*((_QWORD *)this + 14);
      if ( v3 != (void *)-1LL )
        CloseHandle(v3);
      *((_QWORD *)this + 14) = -1;
      CFsrmDuplicatedAutoHandle::CloseTargetHandle((CFsrmFileStream *)((char *)this + 120));
      v4 = (void *)*((_QWORD *)this + 30);
      if ( v4 != (void *)-1LL )
        CloseHandle(v4);
      *((_QWORD *)this + 30) = -1;
      CFsrmDuplicatedAutoHandle::CloseTargetHandle((CFsrmFileStream *)((char *)this + 248));
      v5 = (struct _TP_WAIT *)*((_QWORD *)this + 19);
      if ( v5 )
      {
        CloseThreadpoolWait(v5);
        *((_QWORD *)this + 19) = 0;
      }
      v6 = (void *)*((_QWORD *)this + 18);
      if ( v6 )
        CloseHandle(v6);
      *((_QWORD *)this + 18) = 0;
      *((_QWORD *)this + 23) = 0;
      if ( *((_QWORD *)this + 8) )
        CFsrmFileStream::DeleteTempFile(this);
      *((_QWORD *)this + 33) = 0;
      *((_BYTE *)this + 96) = 0;
    }
    catch ( long v7 )
    {
      CSrmFunctionTracer::HandleHresultException(
        (CSrmFunctionTracer *)v17,
        v7,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::Close",
        0x2BEu,
        v18);
    }
    catch ( _com_error *v9 )
    {
      CSrmFunctionTracer::HandleComException(
        (CSrmFunctionTracer *)v17,
        v9,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::Close",
        0x2BEu,
        v18);
    }
    catch ( std::bad_alloc )
    {
      CSrmFunctionTracer::HandleStdBadAllocException(
        (CSrmFunctionTracer *)v17,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::Close",
        0x2BEu,
        v18);
    }
    catch ( const exception *v10 )
    {
      CSrmFunctionTracer::HandleStdGenericException(
        (CSrmFunctionTracer *)v17,
        v10,
        L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp",
        L"STREAMLC",
        L"CFsrmFileStream::Close",
        0x2BEu,
        v18);
    }
    v17[0] = &CSrmFunctionTracer::`vftable';
  }
  else
  {
    v17[0] = &CSrmFunctionTracer::`vftable';
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v17);
}

```

## disassembly

```asm
0x18005af68  push    rbx
0x18005af6a  sub     rsp, 1B0h
0x18005af71  mov     rax, cs:__security_cookie
0x18005af78  xor     rax, rsp
0x18005af7b  mov     [rsp+1B8h+var_18], rax
0x18005af83  mov     rbx, rcx
0x18005af86  lea     rax, [rsp+1B8h+var_158]
0x18005af8b  mov     [rsp+1B8h+var_170], rax
0x18005af90  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005af97  mov     [rsp+1B8h+var_158], rax
0x18005af9c  lea     rax, aCfsrmfilestrea_4; "CFsrmFileStream::Close"
0x18005afa3  mov     [rsp+1B8h+var_150], rax
0x18005afa8  lea     rax, aStreamlc; "STREAMLC"
0x18005afaf  mov     [rsp+1B8h+var_148], rax
0x18005afb4  mov     [rsp+1B8h+var_140], 29Ch
0x18005afbc  mov     [rsp+1B8h+var_13C], 11h
0x18005afc4  mov     [rsp+1B8h+var_138], 0FFh
0x18005afcf  mov     [rsp+1B8h+var_D0], 1000000h
0x18005afda  xor     edx, edx; Val
0x18005afdc  lea     r8d, [rdx+60h]; Size
0x18005afe0  lea     rcx, [rsp+1B8h+var_130]; void *
0x18005afe8  call    memset_0
0x18005afed  nop
0x18005afee  xor     r8d, r8d
0x18005aff1  lea     rdx, [rsp+1B8h+var_158]
0x18005aff6  lea     rcx, [rsp+1B8h+var_C8]
0x18005affe  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005b003  nop
0x18005b004  cmp     byte ptr [rbx+60h], 0
0x18005b008  jnz     short loc_18005B01E
0x18005b00a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005b011  mov     [rsp+1B8h+var_C8], rax
0x18005b019  jmp     loc_18005B0F2
0x18005b01e  mov     rcx, [rbx+98h]; pwa
0x18005b025  test    rcx, rcx
0x18005b028  jz      short loc_18005B035
0x18005b02a  mov     edx, 1; fCancelPendingCallbacks
0x18005b02f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005b035  mov     rcx, [rbx+70h]; hObject
0x18005b039  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005b03d  jz      short loc_18005B045
0x18005b03f  call    cs:__imp_CloseHandle
0x18005b045  mov     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x18005b04d  lea     rcx, [rbx+78h]; this
0x18005b051  call    ?CloseTargetHandle@CFsrmDuplicatedAutoHandle@@QEAAXXZ; CFsrmDuplicatedAutoHandle::CloseTargetHandle(void)
0x18005b056  mov     rcx, [rbx+0F0h]; hObject
0x18005b05d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005b061  jz      short loc_18005B069
0x18005b063  call    cs:__imp_CloseHandle
0x18005b069  mov     qword ptr [rbx+0F0h], 0FFFFFFFFFFFFFFFFh
0x18005b074  lea     rcx, [rbx+0F8h]; this
0x18005b07b  call    ?CloseTargetHandle@CFsrmDuplicatedAutoHandle@@QEAAXXZ; CFsrmDuplicatedAutoHandle::CloseTargetHandle(void)
0x18005b080  mov     rcx, [rbx+98h]; pwa
0x18005b087  test    rcx, rcx
0x18005b08a  jz      short loc_18005B09D
0x18005b08c  call    cs:__imp_CloseThreadpoolWait
0x18005b092  mov     qword ptr [rbx+98h], 0
0x18005b09d  mov     rcx, [rbx+90h]; hObject
0x18005b0a4  test    rcx, rcx
0x18005b0a7  jz      short loc_18005B0AF
0x18005b0a9  call    cs:__imp_CloseHandle
0x18005b0af  mov     qword ptr [rbx+90h], 0
0x18005b0ba  mov     qword ptr [rbx+0B8h], 0
0x18005b0c5  cmp     qword ptr [rbx+40h], 0
0x18005b0ca  jz      short loc_18005B0D4
0x18005b0cc  mov     rcx, rbx; this
0x18005b0cf  call    ?DeleteTempFile@CFsrmFileStream@@AEAAXXZ; CFsrmFileStream::DeleteTempFile(void)
0x18005b0d4  mov     qword ptr [rbx+108h], 0
0x18005b0df  mov     byte ptr [rbx+60h], 0
0x18005b0e3  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005b0ea  mov     [rsp+1B8h+var_C8], rax
0x18005b0f2  lea     rcx, [rsp+1B8h+var_C8]; this
0x18005b0fa  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005b0ff  nop
0x18005b100  mov     rcx, [rsp+1B8h+var_18]
0x18005b108  xor     rcx, rsp; StackCookie
0x18005b10b  call    __security_check_cookie
0x18005b110  add     rsp, 1B0h
0x18005b117  pop     rbx
0x18005b118  retn
0x18005b119  jmp     short loc_18005B0E3
0x18005b11b  jmp     short loc_18005B0E3
0x18005b11d  jmp     short loc_18005B0E3
```
