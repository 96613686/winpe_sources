# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessReadCompletion(ulong,ulong,IoOperation<CUdpEndpoint> *)

- ea: `0x180019668`
- end: `0x1800197a7`
- name: `?ProcessReadCompletion@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKKKPEAU?$IoOperation@VCUdpEndpoint@@@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(__int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019340`

## callees

- `0x180003944`
- `0x1800191c8`
- `0x180019434`
- `0x180019668`
- `0x18001c11e`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x1800196fa`
- `WS2_32!__imp_ntohs` at `0x180019729`
- `WS2_32!__imp_ntohs` at `0x1800196fa`
- `WS2_32!__imp_ntohs` at `0x180019729`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::ProcessReadCompletion(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4)
{
  unsigned int v4; // ebx
  unsigned int Requests; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // eax
  u_short v13; // ax
  __int64 v14; // rdx

  _InterlockedDecrement((volatile signed __int32 *)(a1 + 428));
  v4 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 68), 0) )
    return 5023;
  Requests = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests();
  ElValidateWin32(Requests, v10, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1979);
  if ( !a2 && a3 )
  {
    v12 = *(_DWORD *)(a4 + 192);
    *(_DWORD *)(a4 + 200) = 0;
    *(_DWORD *)(a4 + 196) = 1052;
    if ( *(_WORD *)(a4 + 64) == 2 )
    {
      if ( v12 >= 0x10 )
      {
        *(_WORD *)(a4 + 208) = ntohs(*(_WORD *)(a4 + 66));
        *(_DWORD *)(a4 + 228) = 4;
        *(_DWORD *)(a4 + 212) = *(_DWORD *)(a4 + 68);
        goto LABEL_12;
      }
    }
    else if ( *(_WORD *)(a4 + 64) == 23 && v12 >= 0x1C )
    {
      v13 = ntohs(*(_WORD *)(a4 + 66));
      *(_DWORD *)(a4 + 228) = 16;
      *(_WORD *)(a4 + 208) = v13;
      memmove_0((void *)(a4 + 212), (const void *)(a4 + 72), 0x10u);
      goto LABEL_12;
    }
    v4 = 13;
LABEL_12:
    if ( !(unsigned int)ElValidateWin32(v4, v11, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1987) )
    {
      *(_DWORD *)(*(_QWORD *)(a4 + 48) + 48LL) = a3;
      CUdpEndpoint::OnIoReadComplete(*(_QWORD *)(a1 + 48), v14, a4, a4 + 196);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180019668  mov     rax, rsp
0x18001966b  mov     [rax+8], rbx
0x18001966f  mov     [rax+10h], rbp
0x180019673  mov     [rax+18h], rsi
0x180019677  mov     [rax+20h], rdi
0x18001967b  push    r14
0x18001967d  sub     rsp, 30h
0x180019681  lock dec dword ptr [rcx+1ACh]
0x180019688  xor     ebx, ebx
0x18001968a  xor     eax, eax
0x18001968c  mov     rdi, r9
0x18001968f  mov     r14d, r8d
0x180019692  mov     esi, edx
0x180019694  mov     rbp, rcx
0x180019697  lock xadd [rcx+44h], eax
0x18001969c  test    eax, eax
0x18001969e  jz      short loc_1800196AA
0x1800196a0  mov     ebx, 139Fh
0x1800196a5  jmp     loc_180019789
0x1800196aa  call    ?PostMaximumReadRequests@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostMaximumReadRequests(void)
0x1800196af  mov     ecx, eax
0x1800196b1  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x1800196b8  mov     r9d, 7BBh
0x1800196be  call    ElValidateWin32
0x1800196c3  test    esi, esi
0x1800196c5  jnz     loc_180019789
0x1800196cb  test    r14d, r14d
0x1800196ce  jz      loc_180019789
0x1800196d4  mov     eax, [rdi+0C0h]
0x1800196da  lea     rsi, [rdi+0C4h]
0x1800196e1  and     [rsi+4], ebx
0x1800196e4  mov     dword ptr [rsi], 41Ch
0x1800196ea  cmp     word ptr [rdi+40h], 2
0x1800196ef  jnz     short loc_180019719
0x1800196f1  cmp     eax, 10h
0x1800196f4  jb      short loc_180019755
0x1800196f6  movzx   ecx, word ptr [rdi+42h]; netshort
0x1800196fa  call    cs:__imp_ntohs
0x180019701  nop     dword ptr [rax+rax+00h]
0x180019706  mov     [rsi+0Ch], ax
0x18001970a  mov     dword ptr [rsi+20h], 4
0x180019711  mov     eax, [rdi+44h]
0x180019714  mov     [rsi+10h], eax
0x180019717  jmp     short loc_18001975A
0x180019719  cmp     word ptr [rdi+40h], 17h
0x18001971e  jnz     short loc_180019755
0x180019720  cmp     eax, 1Ch
0x180019723  jb      short loc_180019755
0x180019725  movzx   ecx, word ptr [rdi+42h]; netshort
0x180019729  call    cs:__imp_ntohs
0x180019730  nop     dword ptr [rax+rax+00h]
0x180019735  lea     rdx, [rdi+48h]; Src
0x180019739  mov     dword ptr [rsi+20h], 10h
0x180019740  lea     rcx, [rsi+10h]; void *
0x180019744  mov     [rsi+0Ch], ax
0x180019748  mov     r8d, 10h; Size
0x18001974e  call    memmove_0
0x180019753  jmp     short loc_18001975A
0x180019755  mov     ebx, 0Dh
0x18001975a  mov     r9d, 7C3h
0x180019760  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019767  mov     ecx, ebx
0x180019769  call    ElValidateWin32
0x18001976e  test    eax, eax
0x180019770  jnz     short loc_180019789
0x180019772  mov     rcx, [rdi+30h]
0x180019776  mov     r9, rsi
0x180019779  mov     r8, rdi
0x18001977c  mov     [rcx+30h], r14d
0x180019780  mov     rcx, [rbp+30h]
0x180019784  call    ?OnIoReadComplete@CUdpEndpoint@@QEAAXPEAV?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@PEAU?$IoOperation@VCUdpEndpoint@@@@PEAUtagWDS_ENDPOINT@@PEAVCMemoryBuffer@@@Z; CUdpEndpoint::OnIoReadComplete(CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>> *,IoOperation<CUdpEndpoint> *,tagWDS_ENDPOINT *,CMemoryBuffer *)
0x180019789  mov     rbp, [rsp+38h+arg_8]
0x18001978e  mov     eax, ebx
0x180019790  mov     rbx, [rsp+38h+arg_0]
0x180019795  mov     rsi, [rsp+38h+arg_10]
0x18001979a  mov     rdi, [rsp+38h+arg_18]
0x18001979f  add     rsp, 30h
0x1800197a3  pop     r14
0x1800197a5  retn
```
