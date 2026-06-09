# CTpSrvQCCState::RecvRequest(tagWDS_ENDPOINT *,CMemoryBuffer *,CMcTpPacket *)

- ea: `0x180010c44`
- end: `0x180010dbf`
- name: `?RecvRequest@CTpSrvQCCState@@QEAAKPEAUtagWDS_ENDPOINT@@PEAVCMemoryBuffer@@PEAVCMcTpPacket@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(CTpSrvQCCState *this, struct tagWDS_ENDPOINT *, void **, struct CMcTpPacket *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180015c34`

## callees

- `0x18000fa3c`
- `0x1800100f8`
- `0x180010c44`
- `0x180016548`
- `0x1800247d4`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180010ccb`
- `KERNEL32!LeaveCriticalSection` at `0x180010d57`
- `KERNEL32!LeaveCriticalSection` at `0x180010ccb`
- `KERNEL32!LeaveCriticalSection` at `0x180010d57`
- `KERNEL32!EnterCriticalSection` at `0x180010cab`
- `KERNEL32!EnterCriticalSection` at `0x180010cab`

## string_xrefs

- `0x180010d1f`: `WDSMCTP[0x%x] QCR Update - Client=0x%x, RTT=%ums`

## pseudocode

```c
__int64 __fastcall CTpSrvQCCState::RecvRequest(
        CTpSrvQCCState *this,
        struct tagWDS_ENDPOINT *a2,
        void **a3,
        struct CMcTpPacket *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  unsigned int v5; // esi
  bool v6; // zf
  unsigned int v10; // r14d
  __int64 v11; // r8
  unsigned int v12; // eax
  struct tagWDS_ENDPOINT *v14; // [rsp+58h] [rbp+10h] BYREF

  v14 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  v5 = 0;
  LOWORD(v14) = 0;
  v6 = *((_BYTE *)a4 + 4) == 5;
  BYTE2(v14) = 0;
  if ( v6 )
  {
    if ( *((_QWORD *)a4 + 407) )
    {
      EnterCriticalSection(v4);
      if ( *((_DWORD *)this + 26) && (v5 = CTpSrvQCR::AddQCR((CTpSrvQCCState *)((char *)this + 48), a4)) != 0 )
      {
        LeaveCriticalSection(v4);
      }
      else
      {
        v10 = CStopwatch::CurrentMs((CTpSrvQCCState *)((char *)this + 112)) - *((_DWORD *)a4 + 818);
        CTpSrvClients::UpdateClient(*((CTpSrvClients **)this + 3), *((_DWORD *)a4 + 812), v10, a4);
        if ( g_ErrLibTraceFunctionEx )
        {
          v11 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 2) + 2216LL), 0);
          g_ErrLibTraceFunctionEx(
            0x10000u,
            L"WDSMCTP[0x%x] QCR Update - Client=0x%x, RTT=%ums",
            v11,
            *((unsigned int *)a4 + 812),
            v10);
        }
        memmove_0(&v14, (char *)a4 + 3312, 3u);
        LeaveCriticalSection(v4);
        v12 = *((_DWORD *)a4 + 824);
        if ( v12 )
        {
          memmove_0(a3[5], (char *)a3[5] + 53, v12);
          *((_DWORD *)a3 + 12) = *((_DWORD *)a4 + 824);
          (*(void (__fastcall **)(_QWORD, _QWORD, void **, struct tagWDS_ENDPOINT **))(**(_QWORD **)(*((_QWORD *)this + 2) + 40LL)
                                                                                     + 24LL))(
            *(_QWORD *)(*((_QWORD *)this + 2) + 40LL),
            *((unsigned int *)a4 + 812),
            a3,
            &v14);
        }
      }
    }
    else
    {
      return CTpSrvClients::ClientQCR(*((CTpSrvClients **)this + 3), (struct CMemoryBuffer *)a3, a4);
    }
  }
  else
  {
    return 13;
  }
  return v5;
}

```

## disassembly

```asm
0x180010c44  mov     rax, rsp
0x180010c47  mov     [rax+8], rbx
0x180010c4b  mov     [rax+18h], rbp
0x180010c4f  mov     [rax+20h], rsi
0x180010c53  mov     [rax+10h], rdx
0x180010c57  push    rdi
0x180010c58  push    r14
0x180010c5a  push    r15
0x180010c5c  sub     rsp, 30h
0x180010c60  mov     rbp, [rcx+8]
0x180010c64  xor     eax, eax
0x180010c66  xor     esi, esi
0x180010c68  mov     [rsp+48h+arg_8], ax
0x180010c6d  cmp     byte ptr [r9+4], 5
0x180010c72  mov     rbx, r9
0x180010c75  mov     r15, r8
0x180010c78  mov     [rsp+48h+arg_A], al
0x180010c7c  mov     rdi, rcx
0x180010c7f  jz      short loc_180010C89
0x180010c81  lea     esi, [rax+0Dh]
0x180010c84  jmp     loc_180010DA4
0x180010c89  cmp     [r9+0CB8h], rax
0x180010c90  jnz     short loc_180010CA8
0x180010c92  mov     rcx, [rcx+18h]; this
0x180010c96  mov     r8, rbx; struct CMcTpPacket *
0x180010c99  mov     rdx, r15; struct CMemoryBuffer *
0x180010c9c  call    ?ClientQCR@CTpSrvClients@@QEAAKPEAVCMemoryBuffer@@PEAVCMcTpPacket@@@Z; CTpSrvClients::ClientQCR(CMemoryBuffer *,CMcTpPacket *)
0x180010ca1  mov     esi, eax
0x180010ca3  jmp     loc_180010DA4
0x180010ca8  mov     rcx, rbp; lpCriticalSection
0x180010cab  call    cs:__imp_EnterCriticalSection
0x180010cb1  cmp     [rdi+68h], esi
0x180010cb4  jz      short loc_180010CD6
0x180010cb6  lea     rcx, [rdi+30h]; this
0x180010cba  mov     rdx, rbx; struct CMcTpPacket *
0x180010cbd  call    ?AddQCR@CTpSrvQCR@@QEAAKPEAVCMcTpPacket@@@Z; CTpSrvQCR::AddQCR(CMcTpPacket *)
0x180010cc2  mov     esi, eax
0x180010cc4  test    eax, eax
0x180010cc6  jz      short loc_180010CD6
0x180010cc8  mov     rcx, rbp; lpCriticalSection
0x180010ccb  call    cs:__imp_LeaveCriticalSection
0x180010cd1  jmp     loc_180010DA4
0x180010cd6  lea     rcx, [rdi+70h]; this
0x180010cda  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x180010cdf  mov     edx, [rbx+0CB0h]; unsigned int
0x180010ce5  mov     r14, rax
0x180010ce8  sub     r14d, [rbx+0CC8h]
0x180010cef  mov     r9, rbx; struct CMcTpPacket *
0x180010cf2  mov     rcx, [rdi+18h]; this
0x180010cf6  mov     r8d, r14d; unsigned int
0x180010cf9  call    ?UpdateClient@CTpSrvClients@@QEAAKKKPEAVCMcTpPacket@@@Z; CTpSrvClients::UpdateClient(ulong,ulong,CMcTpPacket *)
0x180010cfe  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180010d06  jz      short loc_180010D3D
0x180010d08  mov     rcx, [rdi+10h]
0x180010d0c  xor     r8d, r8d
0x180010d0f  lock xadd [rcx+8A8h], r8d
0x180010d18  mov     r9d, [rbx+0CB0h]
0x180010d1f  lea     rdx, aWdsmctp0xXQcrU; "WDSMCTP[0x%x] QCR Update - Client=0x%x,"...
0x180010d26  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180010d2d  mov     ecx, 10000h
0x180010d32  mov     [rsp+48h+var_28], r14d
0x180010d37  call    cs:__guard_dispatch_icall_fptr
0x180010d3d  lea     rdx, [rbx+0CF0h]; Src
0x180010d44  mov     r8d, 3; Size
0x180010d4a  lea     rcx, [rsp+48h+arg_8]; void *
0x180010d4f  call    memmove_0
0x180010d54  mov     rcx, rbp; lpCriticalSection
0x180010d57  call    cs:__imp_LeaveCriticalSection
0x180010d5d  mov     eax, [rbx+0CE0h]
0x180010d63  test    eax, eax
0x180010d65  jz      short loc_180010DA4
0x180010d67  mov     rcx, [r15+28h]; void *
0x180010d6b  mov     r8d, eax; Size
0x180010d6e  lea     rdx, [rcx+35h]; Src
0x180010d72  call    memmove_0
0x180010d77  mov     eax, [rbx+0CE0h]
0x180010d7d  lea     r9, [rsp+48h+arg_8]
0x180010d82  mov     [r15+30h], eax
0x180010d86  mov     r8, r15
0x180010d89  mov     rax, [rdi+10h]
0x180010d8d  mov     edx, [rbx+0CB0h]
0x180010d93  mov     rcx, [rax+28h]
0x180010d97  mov     rax, [rcx]
0x180010d9a  mov     rax, [rax+18h]
0x180010d9e  call    cs:__guard_dispatch_icall_fptr
0x180010da4  mov     rbx, [rsp+48h+arg_0]
0x180010da9  mov     eax, esi
0x180010dab  mov     rsi, [rsp+48h+arg_18]
0x180010db0  mov     rbp, [rsp+48h+arg_10]
0x180010db5  add     rsp, 30h
0x180010db9  pop     r15
0x180010dbb  pop     r14
0x180010dbd  pop     rdi
0x180010dbe  retn
```
