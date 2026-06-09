# winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)

- ea: `0x140052bf8`
- end: `0x140052c0c`
- name: `??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(winrt::Windows::Foundation::IUriRuntimeClass *__hidden this)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14004ec70`
- `0x14004edbc`
- `0x14004ef08`
- `0x14004f020`
- `0x14004f138`
- `0x14004f250`
- `0x14004f39c`
- `0x14004f4b4`
- `0x14004f5cc`
- `0x14004f6e4`
- `0x14004f800`
- `0x14004f91c`
- `0x14004fd98`
- `0x14004fe34`
- `0x14005038c`
- `0x140051920`
- `0x1400519b0`
- `0x140051a3c`
- `0x140051ab8`
- `0x140051c48`
- `0x1400530c0`
- `0x140053190`
- `0x140053fcc`
- `0x1400550d0`
- `0x140055450`
- `0x140057370`
- `0x140057574`
- `0x140057804`
- `0x1400578bc`
- `0x1400579a8`
- `0x140057a74`
- `0x140057e34`
- `0x140058254`
- `0x140058604`
- `0x1400588a0`
- `0x140058a48`
- `0x14005add4`
- `0x14005b068`
- `0x14005b298`
- `0x14005b72c`
- `0x14005b8bc`
- `0x14005bc68`
- `0x14005d614`
- `0x14005ec1c`
- `0x140060b56`
- `0x140063c0a`
- `0x140063d24`
- `0x140063d48`
- `0x140063d7e`
- `0x140063d90`

## callees

- `0x140052bf8`
- `0x14005fcbc`

## pseudocode

```c
void __fastcall winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(
        winrt::Windows::Foundation::IUriRuntimeClass *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x140052bf8  sub     rsp, 28h
0x140052bfc  cmp     qword ptr [rcx], 0
0x140052c00  jz      short loc_140052C07
0x140052c02  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140052c07  add     rsp, 28h
0x140052c0b  retn
```
