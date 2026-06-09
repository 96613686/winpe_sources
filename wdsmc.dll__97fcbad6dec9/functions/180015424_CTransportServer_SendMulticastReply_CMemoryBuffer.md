# CTransportServer::SendMulticastReply(CMemoryBuffer *)

- ea: `0x180015424`
- end: `0x1800154ad`
- name: `?SendMulticastReply@CTransportServer@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `137`
- prototype: `unsigned int __fastcall(CTransportServer *__hidden this, struct CMemoryBuffer *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ea7c`
- `0x18000ec74`
- `0x180010dd0`
- `0x1800112f4`
- `0x1800132cc`
- `0x180013c10`
- `0x180015aa0`

## callees

- `0x180015424`
- `0x1800229c0`
- `0x180025850`

## import_xrefs

- `WDSSRV!WdsSendPacket` at `0x180015463`
- `WDSSRV!WdsSendPacket` at `0x180015463`

## pseudocode

```c
__int64 __fastcall CTransportServer::SendMulticastReply(CTransportServer *this, struct CMemoryBuffer *a2)
{
  unsigned int v3; // ebx
  const char *v4; // rdx
  __int64 v6; // [rsp+20h] [rbp-18h]

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 564, 0) )
  {
    return 5023;
  }
  else
  {
    v3 = WdsSendPacket(
           *((_QWORD *)this + 276),
           (char *)this + 48,
           (char *)this + 1156,
           *((_QWORD *)a2 + 5),
           *((_DWORD *)a2 + 12));
    if ( !(unsigned int)ElValidateWin32(v3, v4, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x24Eu) )
    {
      LODWORD(v6) = *((_DWORD *)a2 + 12);
      CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 4, 0, v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180015424  mov     [rsp+arg_0], rbx
0x180015429  push    rdi
0x18001542a  sub     rsp, 30h
0x18001542e  mov     rdi, rdx
0x180015431  xor     eax, eax
0x180015433  lock xadd [rcx+8D0h], eax
0x18001543b  test    eax, eax
0x18001543d  jz      short loc_180015446
0x18001543f  mov     ebx, 139Fh
0x180015444  jmp     short loc_1800154A0
0x180015446  mov     eax, [rdi+30h]
0x180015449  lea     r8, [rcx+484h]
0x180015450  mov     r9, [rdi+28h]
0x180015454  lea     rdx, [rcx+30h]
0x180015458  mov     rcx, [rcx+8A0h]
0x18001545f  mov     dword ptr [rsp+38h+var_18], eax
0x180015463  call    cs:__imp_WdsSendPacket
0x180015469  mov     r9d, 24Eh; unsigned int
0x18001546f  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015476  mov     ecx, eax; unsigned int
0x180015478  mov     ebx, eax
0x18001547a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001547f  test    eax, eax
0x180015481  jnz     short loc_1800154A0
0x180015483  mov     ecx, [rdi+30h]
0x180015486  lea     edx, [rax+1]; unsigned int
0x180015489  mov     dword ptr [rsp+38h+var_18], ecx
0x18001548d  lea     r8d, [rax+4]
0x180015491  lea     rcx, qword_1800336A0; this
0x180015498  xor     r9d, r9d
0x18001549b  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x1800154a0  mov     eax, ebx
0x1800154a2  mov     rbx, [rsp+38h+arg_0]
0x1800154a7  add     rsp, 30h
0x1800154ab  pop     rdi
0x1800154ac  retn
```
