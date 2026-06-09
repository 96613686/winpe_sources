# CWMFileSinkV1::ProcessCommands(PACKET_PARSE_INFO_EX *,CPayloadMapEntryEx *)

- ea: `0x18000afa0`
- end: `0x18000b11c`
- name: `?ProcessCommands@CWMFileSinkV1@@MEAAJPEAUPACKET_PARSE_INFO_EX@@PEAVCPayloadMapEntryEx@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this, struct PACKET_PARSE_INFO_EX *, struct CPayloadMapEntryEx *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001194`
- `0x18000950c`
- `0x18000afa0`
- `0x18000b400`
- `0x18002b010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000b015`
- `KERNEL32!LeaveCriticalSection` at `0x18000b078`
- `KERNEL32!LeaveCriticalSection` at `0x18000b0e7`
- `KERNEL32!LeaveCriticalSection` at `0x18000b015`
- `KERNEL32!LeaveCriticalSection` at `0x18000b078`
- `KERNEL32!LeaveCriticalSection` at `0x18000b0e7`
- `KERNEL32!EnterCriticalSection` at `0x18000afeb`
- `KERNEL32!EnterCriticalSection` at `0x18000b052`
- `KERNEL32!EnterCriticalSection` at `0x18000b0b9`
- `KERNEL32!EnterCriticalSection` at `0x18000afeb`
- `KERNEL32!EnterCriticalSection` at `0x18000b052`
- `KERNEL32!EnterCriticalSection` at `0x18000b0b9`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::ProcessCommands(
        CWMFileSinkV1 *this,
        struct PACKET_PARSE_INFO_EX *a2,
        struct CPayloadMapEntryEx *a3)
{
  struct PACKET_PARSE_INFO_EX *v4; // r14
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  _QWORD *v7; // rdi
  unsigned int v8; // r12d
  __int64 v9; // rdx
  int v10; // r14d
  __int64 v11; // rdx
  int v12; // r14d
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+38h] [rbp-8h]
  _QWORD *v19; // [rsp+98h] [rbp+58h] BYREF

  v4 = a2;
  if ( a2 && a3 )
  {
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
    v7 = 0;
    v19 = 0;
    v8 = 0;
    v16 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    if ( *((_DWORD *)this + 2112) )
    {
      CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::GetEntry(
        (char *)this + 8424,
        v9,
        &v16,
        &v19);
      v7 = v19;
    }
    LeaveCriticalSection(v6);
    while ( 1 )
    {
      if ( !v7
        || !(*(unsigned int (__fastcall **)(CWMFileSinkV1 *, __int64, struct PACKET_PARSE_INFO_EX *, struct CPayloadMapEntryEx *))(*(_QWORD *)this + 264LL))(
              this,
              v16,
              v4,
              a3) )
      {
        return v8;
      }
      v10 = *(_DWORD *)v7;
      v17 = v7[1];
      EnterCriticalSection(v6);
      operator delete(v7);
      CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::RemoveEntry(
        (char *)this + 8424,
        v11,
        &v16,
        &v19);
      LeaveCriticalSection(v6);
      v12 = v10 - 1;
      if ( v12 )
      {
        if ( v12 != 1 )
          goto LABEL_12;
        v13 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *, __int64))(*(_QWORD *)this + 280LL))(this, v17);
      }
      else
      {
        v13 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *, _QWORD))(*(_QWORD *)this + 272LL))(
                this,
                *((_QWORD *)this + 34));
      }
      v8 = v13;
LABEL_12:
      EnterCriticalSection(v6);
      if ( *((_DWORD *)this + 2112) )
      {
        CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::GetEntry(
          (char *)this + 8424,
          v14,
          &v16,
          &v19);
        v7 = v19;
      }
      else
      {
        v7 = 0;
        v19 = 0;
      }
      LeaveCriticalSection(v6);
      v4 = a2;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000afa0  mov     [rsp-38h+arg_0], rbx
0x18000afa5  mov     [rsp-38h+arg_8], rdx
0x18000afaa  push    rbp
0x18000afab  push    rsi
0x18000afac  push    rdi
0x18000afad  push    r12
0x18000afaf  push    r13
0x18000afb1  push    r14
0x18000afb3  push    r15
0x18000afb5  mov     rbp, rsp
0x18000afb8  sub     rsp, 40h
0x18000afbc  mov     r13, r8
0x18000afbf  mov     r14, rdx
0x18000afc2  mov     rsi, rcx
0x18000afc5  test    rdx, rdx
0x18000afc8  jz      loc_18000B0FF
0x18000afce  test    r8, r8
0x18000afd1  jz      loc_18000B0FF
0x18000afd7  lea     rbx, [rcx+60h]
0x18000afdb  xor     edi, edi
0x18000afdd  mov     rcx, rbx; lpCriticalSection
0x18000afe0  mov     [rbp+arg_18], rdi
0x18000afe4  xor     r12d, r12d
0x18000afe7  mov     [rbp+var_10], rdi
0x18000afeb  call    cs:__imp_EnterCriticalSection
0x18000aff1  lea     r15, [rsi+20E8h]
0x18000aff8  cmp     [r15+18h], edi
0x18000affc  jz      short loc_18000B012
0x18000affe  lea     r9, [rbp+arg_18]
0x18000b002  mov     rcx, r15
0x18000b005  lea     r8, [rbp+var_10]
0x18000b009  call    ?GetEntry@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@QEBAHHAEA_KAEAPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@Z; CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::GetEntry(int,unsigned __int64 &,CWMFileSinkV1::WRITER_SINK_COMMAND * &)
0x18000b00e  mov     rdi, [rbp+arg_18]
0x18000b012  mov     rcx, rbx; lpCriticalSection
0x18000b015  call    cs:__imp_LeaveCriticalSection
0x18000b01b  jmp     loc_18000B0F1
0x18000b020  mov     rax, [rsi]
0x18000b023  mov     r9, r13
0x18000b026  mov     rdx, [rbp+var_10]
0x18000b02a  mov     r8, r14
0x18000b02d  mov     rcx, rsi
0x18000b030  mov     rax, [rax+108h]
0x18000b037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b03c  test    eax, eax
0x18000b03e  jz      loc_18000B0FA
0x18000b044  mov     rax, [rdi+8]
0x18000b048  mov     rcx, rbx; lpCriticalSection
0x18000b04b  mov     r14d, [rdi]
0x18000b04e  mov     [rbp+var_8], rax
0x18000b052  call    cs:__imp_EnterCriticalSection
0x18000b058  mov     edx, 10h; unsigned __int64
0x18000b05d  mov     rcx, rdi; void *
0x18000b060  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b065  lea     r9, [rbp+arg_18]
0x18000b069  mov     rcx, r15
0x18000b06c  lea     r8, [rbp+var_10]
0x18000b070  call    ?RemoveEntry@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@QEAAHHAEA_KAEAPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@Z; CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::RemoveEntry(int,unsigned __int64 &,CWMFileSinkV1::WRITER_SINK_COMMAND * &)
0x18000b075  mov     rcx, rbx; lpCriticalSection
0x18000b078  call    cs:__imp_LeaveCriticalSection
0x18000b07e  sub     r14d, 1
0x18000b082  jz      short loc_18000B09A
0x18000b084  cmp     r14d, 1
0x18000b088  jnz     short loc_18000B0B6
0x18000b08a  mov     rax, [rsi]
0x18000b08d  mov     rdx, [rbp+var_8]
0x18000b091  mov     rax, [rax+118h]
0x18000b098  jmp     short loc_18000B0AB
0x18000b09a  mov     rax, [rsi]
0x18000b09d  mov     rdx, [rsi+110h]
0x18000b0a4  mov     rax, [rax+110h]
0x18000b0ab  mov     rcx, rsi
0x18000b0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b3  mov     r12d, eax
0x18000b0b6  mov     rcx, rbx; lpCriticalSection
0x18000b0b9  call    cs:__imp_EnterCriticalSection
0x18000b0bf  cmp     dword ptr [rsi+2100h], 0
0x18000b0c6  jz      short loc_18000B0DE
0x18000b0c8  lea     r9, [rbp+arg_18]
0x18000b0cc  mov     rcx, r15
0x18000b0cf  lea     r8, [rbp+var_10]
0x18000b0d3  call    ?GetEntry@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@QEBAHHAEA_KAEAPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@Z; CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::GetEntry(int,unsigned __int64 &,CWMFileSinkV1::WRITER_SINK_COMMAND * &)
0x18000b0d8  mov     rdi, [rbp+arg_18]
0x18000b0dc  jmp     short loc_18000B0E4
0x18000b0de  xor     edi, edi
0x18000b0e0  mov     [rbp+arg_18], rdi
0x18000b0e4  mov     rcx, rbx; lpCriticalSection
0x18000b0e7  call    cs:__imp_LeaveCriticalSection
0x18000b0ed  mov     r14, [rbp+arg_8]
0x18000b0f1  test    rdi, rdi
0x18000b0f4  jnz     loc_18000B020
0x18000b0fa  mov     eax, r12d
0x18000b0fd  jmp     short loc_18000B104
0x18000b0ff  mov     eax, 80070057h
0x18000b104  mov     rbx, [rsp+40h+arg_0]
0x18000b10c  add     rsp, 40h
0x18000b110  pop     r15
0x18000b112  pop     r14
0x18000b114  pop     r13
0x18000b116  pop     r12
0x18000b118  pop     rdi
0x18000b119  pop     rsi
0x18000b11a  pop     rbp
0x18000b11b  retn
```
