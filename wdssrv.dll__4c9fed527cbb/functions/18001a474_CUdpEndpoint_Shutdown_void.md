# CUdpEndpoint::Shutdown(void)

- ea: `0x18001a474`
- end: `0x18001a541`
- name: `?Shutdown@CUdpEndpoint@@QEAAKXZ`
- size: `205`
- prototype: `unsigned int __fastcall(CUdpEndpoint *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180002798`
- `0x180002c24`
- `0x180003680`
- `0x18001823c`
- `0x1800192a0`

## callees

- `0x180003944`
- `0x180016e5c`
- `0x18001784c`
- `0x18001a250`
- `0x18001a474`
- `0x18001b418`

## pseudocode

```c
__int64 __fastcall CUdpEndpoint::Shutdown(CUdpEndpoint *this)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  struct tagWDS_IP_ADDRESS6 *v5; // rdx
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  unsigned int v11; // eax

  _InterlockedExchange((volatile __int32 *)this + 22, 1);
  v2 = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown((__int64)this + 96);
  ElValidateWin32(v2, v3, (__int64)"base\\eco\\wds\\wdssrv\\server\\src\\udpendpoint.cpp", 0x135u);
  if ( *((_DWORD *)this + 574) )
  {
    v4 = *((_QWORD *)this + 10);
    v5 = (CUdpEndpoint *)((char *)this + 800);
    if ( *((_DWORD *)this + 204) == 16 )
    {
      v7 = CStaticMulticastLeaseHandler::RetrurnLease((LPCRITICAL_SECTION)(v4 + 128), v5);
      v9 = 320;
      v10 = v7;
    }
    else
    {
      if ( *((_DWORD *)this + 204) != 4 )
      {
        v7 = 13;
        goto LABEL_11;
      }
      if ( *(_DWORD *)v4 )
        v11 = CMadcapHandler::ReleaseLease((LPCRITICAL_SECTION)(v4 + 248), v5);
      else
        v11 = CStaticMulticastLeaseHandler::RetrurnLease((LPCRITICAL_SECTION)(v4 + 8), v5);
      v7 = v11;
      v9 = 331;
      v10 = v11;
    }
    ElValidateWin32_9(v10, v6, v8, v9);
LABEL_11:
    ElValidateWin32(v7, (__int64)v5, (__int64)"base\\eco\\wds\\wdssrv\\server\\src\\udpendpoint.cpp", 0x13Fu);
    *((_DWORD *)this + 204) = 0;
    *((_DWORD *)this + 574) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001a474  mov     [rsp+arg_0], rbx
0x18001a479  push    rdi
0x18001a47a  sub     rsp, 20h
0x18001a47e  mov     eax, 1
0x18001a483  mov     rdi, rcx
0x18001a486  xchg    eax, [rcx+58h]
0x18001a489  add     rcx, 60h ; '`'
0x18001a48d  call    ?Shutdown@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Shutdown(void)
0x18001a492  mov     ecx, eax
0x18001a494  lea     r8, aBaseEcoWdsWdss_5; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x18001a49b  mov     r9d, 135h
0x18001a4a1  call    ElValidateWin32
0x18001a4a6  cmp     dword ptr [rdi+8F8h], 0
0x18001a4ad  jz      loc_18001A533
0x18001a4b3  mov     rcx, [rdi+50h]
0x18001a4b7  lea     rdx, [rdi+320h]; Buf2
0x18001a4be  cmp     dword ptr [rdx+10h], 10h
0x18001a4c2  jnz     short loc_18001A4D9
0x18001a4c4  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18001a4c8  call    ?RetrurnLease@CStaticMulticastLeaseHandler@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CStaticMulticastLeaseHandler::RetrurnLease(tagWDS_IP_ADDRESS6 *)
0x18001a4cd  mov     ebx, eax
0x18001a4cf  mov     r9d, 140h
0x18001a4d5  mov     ecx, eax
0x18001a4d7  jmp     short loc_18001A505
0x18001a4d9  cmp     dword ptr [rdx+10h], 4
0x18001a4dd  jnz     short loc_18001A50C
0x18001a4df  cmp     dword ptr [rcx], 0
0x18001a4e2  jnz     short loc_18001A4EF
0x18001a4e4  add     rcx, 8; lpCriticalSection
0x18001a4e8  call    ?RetrurnLease@CStaticMulticastLeaseHandler@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CStaticMulticastLeaseHandler::RetrurnLease(tagWDS_IP_ADDRESS6 *)
0x18001a4ed  jmp     short loc_18001A4FB
0x18001a4ef  add     rcx, 0F8h; lpCriticalSection
0x18001a4f6  call    ?ReleaseLease@CMadcapHandler@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CMadcapHandler::ReleaseLease(tagWDS_IP_ADDRESS6 *)
0x18001a4fb  mov     ebx, eax
0x18001a4fd  mov     r9d, 14Bh
0x18001a503  mov     ecx, eax
0x18001a505  call    ElValidateWin32_9
0x18001a50a  jmp     short loc_18001A511
0x18001a50c  mov     ebx, 0Dh
0x18001a511  mov     r9d, 13Fh
0x18001a517  lea     r8, aBaseEcoWdsWdss_5; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x18001a51e  mov     ecx, ebx
0x18001a520  call    ElValidateWin32
0x18001a525  and     dword ptr [rdi+330h], 0
0x18001a52c  and     dword ptr [rdi+8F8h], 0
0x18001a533  mov     rbx, [rsp+28h+arg_0]
0x18001a538  xor     eax, eax
0x18001a53a  add     rsp, 20h
0x18001a53e  pop     rdi
0x18001a53f  retn
```
