# CASFScriptCommandObjectv2::~CASFScriptCommandObjectv2(void)

- ea: `0x18000cc88`
- end: `0x18000ccde`
- name: `??1CASFScriptCommandObjectv2@@UEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CASFScriptCommandObjectv2 *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cd00`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18000c1d4`
- `0x18001d6f0`

## pseudocode

```c
void __fastcall CASFScriptCommandObjectv2::~CASFScriptCommandObjectv2(CASFScriptCommandObjectv2 *this)
{
  struct IWMSCriticalSection **v2; // rcx
  char v3; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CASFScriptCommandObjectv2::`vftable'{for `IASFScriptCommandObject'};
  v2 = (struct IWMSCriticalSection **)((char *)this + 8);
  *v2 = (struct IWMSCriticalSection *)&CASFScriptCommandObjectv2::`vftable'{for `IASFUnknownPriv'};
  *((_QWORD *)this + 2) = &CASFScriptCommandObjectv2::`vftable'{for `CPoolReleaseItem'};
  CASFScriptCommandObjectBase::Shutdown(v2);
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v3, *((struct IWMSCriticalSection **)this + 4));
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v3);
  CASFScriptCommandObjectBase::~CASFScriptCommandObjectBase(this);
}

```

## disassembly

```asm
0x18000cc88  push    rbx
0x18000cc8a  sub     rsp, 20h
0x18000cc8e  mov     rbx, rcx
0x18000cc91  lea     rax, ??_7CASFScriptCommandObjectv2@@6BIASFScriptCommandObject@@@; const CASFScriptCommandObjectv2::`vftable'{for `IASFScriptCommandObject'}
0x18000cc98  mov     [rcx], rax
0x18000cc9b  add     rcx, 8; this
0x18000cc9f  lea     rax, ??_7CASFScriptCommandObjectv2@@6BIASFUnknownPriv@@@; const CASFScriptCommandObjectv2::`vftable'{for `IASFUnknownPriv'}
0x18000cca6  mov     [rcx], rax
0x18000cca9  lea     rax, ??_7CASFScriptCommandObjectv2@@6BCPoolReleaseItem@@@; const CASFScriptCommandObjectv2::`vftable'{for `CPoolReleaseItem'}
0x18000ccb0  mov     [rbx+10h], rax
0x18000ccb4  call    ?Shutdown@CASFScriptCommandObjectBase@@UEAAJXZ; CASFScriptCommandObjectBase::Shutdown(void)
0x18000ccb9  mov     rdx, [rbx+20h]; struct IWMSCriticalSection *
0x18000ccbd  lea     rcx, [rsp+28h+arg_0]; this
0x18000ccc2  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000ccc7  lea     rcx, [rsp+28h+arg_0]; this
0x18000cccc  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000ccd1  mov     rcx, rbx; this
0x18000ccd4  add     rsp, 20h
0x18000ccd8  pop     rbx
0x18000ccd9  jmp     ??1CASFScriptCommandObjectBase@@UEAA@XZ; CASFScriptCommandObjectBase::~CASFScriptCommandObjectBase(void)
```
