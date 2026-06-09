# CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)

- ea: `0x10041da80`
- end: `0x10041dc3e`
- name: `?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z`
- size: `446`
- prototype: `unsigned int __fastcall(struct CCriticalSectionSOS **)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10041e5b0`
- `0x100422bc0`
- `0x100424a20`
- `0x10042d610`
- `0x100431020`
- `0x100437180`
- `0x10043add0`
- `0x100443a70`
- `0x100449b20`
- `0x100454230`
- `0x100455bf0`
- `0x100456900`
- `0x100457d00`

## callees

- `0x10041da80`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041db0c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041dbbf`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041db0c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041dbbf`
- `sqldk!SystemThread_TlsIndex` at `0x10041daaa`
- `sqldk!SystemThread_TlsIndex` at `0x10041db5d`
- `sqldk!SystemThread_TlsOffset` at `0x10041dab3`
- `sqldk!SystemThread_TlsOffset` at `0x10041db66`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041dace`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041db81`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041dace`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041db81`

## string_xrefs

- `0x10041dafc`: `sql\common\dk\sni\include\sni_common.hpp`
- `0x10041dbaf`: `sql\common\dk\sni\include\sni_common.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCriticalSectionSOS::Initialize(struct CCriticalSectionSOS **a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  struct CCriticalSectionSOS *v4; // rdi
  __int64 v6; // rbp
  __int64 v7; // rax
  _QWORD *v8; // rax

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  v4 = (struct CCriticalSectionSOS *)operator new(
                                       0x20u,
                                       *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v3 + 992) + 56LL) + 8LL),
                                       1,
                                       "sql\\common\\dk\\sni\\include\\sni_common.hpp",
                                       424,
                                       6u);
  if ( v4 )
  {
    *(_QWORD *)v4 = &CCriticalSectionSOS::`vftable';
    *((_QWORD *)v4 + 1) = 0;
  }
  else
  {
    v4 = 0;
  }
  *a1 = v4;
  if ( !v4 )
    return 14;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = operator new(
         0x40u,
         *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v7 + 992) + 56LL) + 8LL),
         1,
         "sql\\common\\dk\\sni\\include\\sni_common.hpp",
         380,
         6u);
  if ( v8 )
  {
    v8[2] = v8 + 1;
    v8[1] = v8 + 1;
    v8[3] = 0;
    *v8 = &SOS_UnfairRecursiveMutexExtendedGuarantee::`vftable';
    v8[4] = 0;
    v8[5] = 0;
    v8[7] = 0;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)v4 + 1) = v8;
  if ( v8 )
    return 0;
  if ( *a1 )
    (**(void (__fastcall ***)(_QWORD, __int64))*a1)(*a1, 1);
  *a1 = 0;
  return 14;
}

```

## disassembly

```asm
0x10041da80  push    rbp
0x10041da82  push    rsi
0x10041da83  push    rdi
0x10041da84  sub     rsp, 40h
0x10041da88  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x10041da91  mov     [rsp+58h+arg_18], rbx
0x10041da96  mov     rsi, rcx
0x10041da99  mov     [rsp+58h+arg_0], 1A8h
0x10041daa1  mov     r8, gs:58h
0x10041daaa  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041dab1  mov     edx, [rax]
0x10041dab3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041daba  mov     ebx, [rax]
0x10041dabc  add     rbx, [r8+rdx*8]
0x10041dac0  mov     rax, [rbx+100h]
0x10041dac7  test    rax, rax
0x10041daca  jnz     short loc_10041DADB
0x10041dacc  xor     ecx, ecx
0x10041dace  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041dad4  mov     rax, [rbx+100h]
0x10041dadb  mov     rax, [rax+3E0h]
0x10041dae2  mov     rcx, [rax+38h]
0x10041dae6  mov     rdx, [rcx+8]
0x10041daea  mov     [rsp+58h+arg_8], rdx
0x10041daef  mov     [rsp+58h+var_30], 6
0x10041daf4  mov     [rsp+58h+var_38], 1A8h
0x10041dafc  lea     r9, aSqlCommonDkSni_14; "sql\\common\\dk\\sni\\include\\sni_comm"...
0x10041db03  mov     ecx, 20h ; ' '
0x10041db08  lea     r8d, [rcx-1Fh]
0x10041db0c  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10041db12  mov     rdi, rax
0x10041db15  mov     [rsp+58h+arg_10], rax
0x10041db1a  xor     ebx, ebx
0x10041db1c  test    rax, rax
0x10041db1f  jz      short loc_10041DB31
0x10041db21  lea     rax, ??_7CCriticalSectionSOS@@6B@; const CCriticalSectionSOS::`vftable'
0x10041db28  mov     [rdi], rax
0x10041db2b  mov     [rdi+8], rbx
0x10041db2f  jmp     short loc_10041DB34
0x10041db31  mov     rdi, rbx
0x10041db34  mov     [rsi], rdi
0x10041db37  test    rdi, rdi
0x10041db3a  jnz     short loc_10041DB4C
0x10041db3c  lea     eax, [rdi+0Eh]
0x10041db3f  mov     rbx, [rsp+58h+arg_18]
0x10041db44  add     rsp, 40h
0x10041db48  pop     rdi
0x10041db49  pop     rsi
0x10041db4a  pop     rbp
0x10041db4b  retn
0x10041db4c  mov     [rsp+58h+arg_0], 17Ch
0x10041db54  mov     rdx, gs:58h
0x10041db5d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041db64  mov     ecx, [rax]
0x10041db66  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041db6d  mov     ebp, [rax]
0x10041db6f  add     rbp, [rdx+rcx*8]
0x10041db73  mov     rax, [rbp+100h]
0x10041db7a  test    rax, rax
0x10041db7d  jnz     short loc_10041DB8E
0x10041db7f  xor     ecx, ecx
0x10041db81  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041db87  mov     rax, [rbp+100h]
0x10041db8e  mov     rax, [rax+3E0h]
0x10041db95  mov     rcx, [rax+38h]
0x10041db99  mov     rdx, [rcx+8]
0x10041db9d  mov     [rsp+58h+arg_8], rdx
0x10041dba2  mov     [rsp+58h+var_30], 6
0x10041dba7  mov     [rsp+58h+var_38], 17Ch
0x10041dbaf  lea     r9, aSqlCommonDkSni_14; "sql\\common\\dk\\sni\\include\\sni_comm"...
0x10041dbb6  mov     ecx, 40h ; '@'
0x10041dbbb  lea     r8d, [rcx-3Fh]
0x10041dbbf  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10041dbc5  mov     [rsp+58h+arg_10], rax
0x10041dbca  test    rax, rax
0x10041dbcd  jz      short loc_10041DBF6
0x10041dbcf  lea     rcx, [rax+8]
0x10041dbd3  mov     [rcx+8], rcx
0x10041dbd7  mov     [rcx], rcx
0x10041dbda  mov     [rax+18h], rbx
0x10041dbde  lea     rcx, ??_7SOS_UnfairRecursiveMutexExtendedGuarantee@@6B@; const SOS_UnfairRecursiveMutexExtendedGuarantee::`vftable'
0x10041dbe5  mov     [rax], rcx
0x10041dbe8  mov     [rax+20h], rbx
0x10041dbec  mov     [rax+28h], rbx
0x10041dbf0  mov     [rax+38h], rbx
0x10041dbf4  jmp     short loc_10041DBF9
0x10041dbf6  mov     rax, rbx
0x10041dbf9  mov     [rdi+8], rax
0x10041dbfd  mov     edi, 0Eh
0x10041dc02  test    rax, rax
0x10041dc05  cmovnz  edi, ebx
0x10041dc08  jnz     short loc_10041DC2F
0x10041dc0a  mov     rcx, [rsi]
0x10041dc0d  test    rcx, rcx
0x10041dc10  jz      short loc_10041DC1D
0x10041dc12  mov     r8, [rcx]
0x10041dc15  mov     edx, 1
0x10041dc1a  call    qword ptr [r8]
0x10041dc1d  mov     [rsi], rbx
0x10041dc20  mov     eax, edi
0x10041dc22  mov     rbx, [rsp+58h+arg_18]
0x10041dc27  add     rsp, 40h
0x10041dc2b  pop     rdi
0x10041dc2c  pop     rsi
0x10041dc2d  pop     rbp
0x10041dc2e  retn
0x10041dc2f  xor     eax, eax
0x10041dc31  mov     rbx, [rsp+58h+arg_18]
0x10041dc36  add     rsp, 40h
0x10041dc3a  pop     rdi
0x10041dc3b  pop     rsi
0x10041dc3c  pop     rbp
0x10041dc3d  retn
```
