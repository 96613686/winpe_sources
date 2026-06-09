# LogSessHandlerPasswdGet

- ea: `0x18002272c`
- end: `0x18002284a`
- name: `LogSessHandlerPasswdGet`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001bb0`

## callees

- `0x180006d00`
- `0x18000ad50`
- `0x180011fec`
- `0x1800185b8`
- `0x18002272c`

## import_xrefs

- `LSASRV!LsaIEventWritePackageNoCredential` at `0x180022804`
- `LSASRV!LsaIEventWritePackageNoCredential` at `0x180022804`

## pseudocode

```c
__int64 __fastcall LogSessHandlerPasswdGet(__int64 a1, __int64 a2)
{
  _BYTE *v4; // rax
  __int64 v5; // rcx
  _QWORD v7[3]; // [rsp+30h] [rbp-18h] BYREF

  v7[0] = 1048590;
  v7[1] = L"WDigest";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids);
  v4 = *(_BYTE **)(a2 + 8);
  if ( v4 )
  {
    v5 = *(unsigned __int16 *)(a2 + 2);
    if ( *(_WORD *)(a2 + 2) )
    {
      do
      {
        *v4++ = 0;
        --v5;
      }
      while ( v5 );
    }
    UnicodeStringFree(a2);
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDigestSSO>::__private_IsEnabledPreCheck(
    `wil::Feature<__WilFeatureTraits_Feature_DisableDigestSSO>::GetImpl'::`2'::impl,
    a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids, 2148074254LL);
  ((void (__fastcall *)(_QWORD *, __int64, __int64, _QWORD, _DWORD, int))LsaIEventWritePackageNoCredential)(
    v7,
    a1 + 48,
    a1 + 64,
    0,
    0,
    -2146893042);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids, 2148074254LL);
  return 2148074254LL;
}

```

## disassembly

```asm
0x18002272c  mov     r11, rsp
0x18002272f  mov     [r11+8], rbx
0x180022733  mov     [r11+10h], rdi
0x180022737  push    r14
0x180022739  sub     rsp, 40h
0x18002273d  lea     rax, aWdigest; "WDigest"
0x180022744  mov     qword ptr [r11-18h], 10000Eh
0x18002274c  mov     [r11-10h], rax
0x180022750  mov     rbx, rdx
0x180022753  mov     rdi, rcx
0x180022756  mov     rcx, cs:WPP_GLOBAL_Control
0x18002275d  lea     r14, WPP_GLOBAL_Control
0x180022764  cmp     rcx, r14
0x180022767  jz      short loc_180022784
0x180022769  test    byte ptr [rcx+1Ch], 80h
0x18002276d  jz      short loc_180022784
0x18002276f  mov     rcx, [rcx+10h]
0x180022773  lea     r8, WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids
0x18002277a  mov     edx, 1Dh
0x18002277f  call    WPP_SF_
0x180022784  mov     rax, [rbx+8]
0x180022788  test    rax, rax
0x18002278b  jz      short loc_1800227AA
0x18002278d  movzx   ecx, word ptr [rbx+2]
0x180022791  test    rcx, rcx
0x180022794  jz      short loc_1800227A2
0x180022796  mov     byte ptr [rax], 0
0x180022799  inc     rax
0x18002279c  sub     rcx, 1
0x1800227a0  jnz     short loc_180022796
0x1800227a2  mov     rcx, rbx
0x1800227a5  call    UnicodeStringFree
0x1800227aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableDigestSSO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDigestSSO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDigestSSO> `wil::Feature<__WilFeatureTraits_Feature_DisableDigestSSO>::GetImpl(void)'::`2'::impl
0x1800227b1  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDigestSSO@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDigestSSO>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800227b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227bd  cmp     rcx, r14
0x1800227c0  jz      short loc_1800227E3
0x1800227c2  test    byte ptr [rcx+1Ch], 1
0x1800227c6  jz      short loc_1800227E3
0x1800227c8  mov     rcx, [rcx+10h]
0x1800227cc  lea     r8, WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids
0x1800227d3  mov     edx, 1Eh
0x1800227d8  mov     r9d, 8009030Eh
0x1800227de  call    WPP_SF_d
0x1800227e3  mov     ebx, 8009030Eh
0x1800227e8  lea     r8, [rdi+40h]
0x1800227ec  mov     [rsp+48h+var_20], ebx
0x1800227f0  lea     rdx, [rdi+30h]
0x1800227f4  xor     r9d, r9d
0x1800227f7  mov     [rsp+48h+var_28], 0
0x1800227ff  lea     rcx, [rsp+48h+var_18]
0x180022804  call    cs:__imp_LsaIEventWritePackageNoCredential
0x18002280a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022811  cmp     rcx, r14
0x180022814  jz      short loc_180022837
0x180022816  test    byte ptr [rcx+1Ch], 80h
0x18002281a  jz      short loc_180022837
0x18002281c  mov     rcx, [rcx+10h]
0x180022820  lea     r8, WPP_41b543b89e003294ee403a89aa4a15ce_Traceguids
0x180022827  mov     edx, 22h ; '"'
0x18002282c  mov     r9d, 8009030Eh
0x180022832  call    WPP_SF_d
0x180022837  mov     rdi, [rsp+48h+arg_8]
0x18002283c  mov     eax, ebx
0x18002283e  mov     rbx, [rsp+48h+arg_0]
0x180022843  add     rsp, 40h
0x180022847  pop     r14
0x180022849  retn
```
