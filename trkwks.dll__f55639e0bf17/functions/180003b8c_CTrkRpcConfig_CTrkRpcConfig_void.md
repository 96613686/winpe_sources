# CTrkRpcConfig::CTrkRpcConfig(void)

- ea: `0x180003b8c`
- end: `0x180003bf7`
- name: `??0CTrkRpcConfig@@IEAA@XZ`
- size: `107`
- prototype: `CTrkRpcConfig *__fastcall(CTrkRpcConfig *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003684`
- `0x180004f60`
- `0x18000f7dc`

## callees

- `0x1800020a4`
- `0x180003b8c`
- `0x180007440`
- `0x18000a09c`

## pseudocode

```c
CTrkRpcConfig *__fastcall CTrkRpcConfig::CTrkRpcConfig(CTrkRpcConfig *this)
{
  bool v2; // zf
  const unsigned __int16 *v4; // r9
  const unsigned __int16 *v5; // r9

  v2 = CTrkRpcConfig::_fInitialized == 0;
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( v2 )
  {
    CTrkConfiguration::Initialize(this);
    CTrkConfiguration::Read(this, L"CustomDcName", (struct CMultiTsz *)&CTrkRpcConfig::_mtszCustomDcName, v4);
    CTrkConfiguration::Read(this, L"CustomSecureDcName", (struct CMultiTsz *)CTrkRpcConfig::_mtszCustomSecureDcName, v5);
    CTrkRpcConfig::_fInitialized = 1;
    CTrkConfiguration::UnInitialize(this);
  }
  return this;
}

```

## disassembly

```asm
0x180003b8c  push    rbx
0x180003b8e  sub     rsp, 20h
0x180003b92  xor     eax, eax
0x180003b94  mov     rbx, rcx
0x180003b97  cmp     cs:?_fInitialized@CTrkRpcConfig@@1HA, eax; int CTrkRpcConfig::_fInitialized
0x180003b9d  mov     [rcx], eax
0x180003b9f  mov     [rcx+8], rax
0x180003ba3  mov     [rcx+10h], rax
0x180003ba7  jz      short loc_180003BB2
0x180003ba9  mov     rax, rbx
0x180003bac  add     rsp, 20h
0x180003bb0  pop     rbx
0x180003bb1  retn
0x180003bb2  call    ?Initialize@CTrkConfiguration@@QEAAXXZ; CTrkConfiguration::Initialize(void)
0x180003bb7  lea     r8, ?_mtszCustomDcName@CTrkRpcConfig@@1VCMultiTsz@@A; struct CMultiTsz *
0x180003bbe  mov     rcx, rbx; this
0x180003bc1  lea     rdx, aCustomdcname; "CustomDcName"
0x180003bc8  call    ?Read@CTrkConfiguration@@IEBAXPEBGPEAVCMultiTsz@@0@Z; CTrkConfiguration::Read(ushort const *,CMultiTsz *,ushort const *)
0x180003bcd  lea     r8, ?_mtszCustomSecureDcName@CTrkRpcConfig@@1VCMultiTsz@@A; struct CMultiTsz *
0x180003bd4  mov     rcx, rbx; this
0x180003bd7  lea     rdx, aCustomsecuredc; "CustomSecureDcName"
0x180003bde  call    ?Read@CTrkConfiguration@@IEBAXPEBGPEAVCMultiTsz@@0@Z; CTrkConfiguration::Read(ushort const *,CMultiTsz *,ushort const *)
0x180003be3  mov     rcx, rbx; this
0x180003be6  mov     cs:?_fInitialized@CTrkRpcConfig@@1HA, 1; int CTrkRpcConfig::_fInitialized
0x180003bf0  call    ?UnInitialize@CTrkConfiguration@@QEAAXXZ; CTrkConfiguration::UnInitialize(void)
0x180003bf5  jmp     short loc_180003BA9
```
