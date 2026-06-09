# CAttachmentServices::_SaveHelper(HWND__ *)

- ea: `0x18001143c`
- end: `0x1800114bb`
- name: `?_SaveHelper@CAttachmentServices@@AEAAJPEAUHWND__@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(CAttachmentServices *__hidden this, HWND hWndParent)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x180010280`
- `0x1800102a0`

## callees

- `0x1800022f0`
- `0x180003080`
- `0x1800030e0`
- `0x180003f30`
- `0x18000cf8c`
- `0x180010dbc`
- `0x180010e3c`
- `0x1800110cc`
- `0x180011148`
- `0x18001143c`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::_SaveHelper(CAttachmentServices *this, HWND hWndParent)
{
  CAttachmentServices *v4; // rcx
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 1) = 0;
  v6 = 0;
  if ( (unsigned int)CAttachmentServices::PushOp(this, 5, &v6) )
  {
    CAttachmentServices::_OpStaticFileTypeTrust(v4);
    CAttachmentServices::_OpValidateLocalPath(this);
    CAttachmentServices::_OpTrustedHandler(this);
    CAttachmentServices::_OpZoneCheck(this);
    CAttachmentServices::_OpAntiVirus(this, hWndParent);
    CAttachmentServices::_OpZoneMarking(this);
    CAttachmentServices::PopOp(this, v6);
  }
  return CAttachmentServices::DetailedResult((LPARAM)this, hWndParent);
}

```

## disassembly

```asm
0x18001143c  mov     [rsp+arg_8], rbx
0x180011441  push    rdi
0x180011442  sub     rsp, 20h
0x180011446  xor     r9d, r9d
0x180011449  lea     r8, [rsp+28h+arg_0]
0x18001144e  mov     rdi, rdx
0x180011451  mov     [rcx+8], r9
0x180011455  mov     rbx, rcx
0x180011458  mov     [rsp+28h+arg_0], r9d
0x18001145d  lea     edx, [r9+5]
0x180011461  call    ?PushOp@CAttachmentServices@@AEAAHW4ATTACHMENT_OP@@PEAW42@@Z; CAttachmentServices::PushOp(ATTACHMENT_OP,ATTACHMENT_OP *)
0x180011466  test    eax, eax
0x180011468  jz      short loc_1800114A6
0x18001146a  call    ?_OpStaticFileTypeTrust@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpStaticFileTypeTrust(void)
0x18001146f  mov     rcx, rbx; this
0x180011472  call    ?_OpValidateLocalPath@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpValidateLocalPath(void)
0x180011477  mov     rcx, rbx; this
0x18001147a  call    ?_OpTrustedHandler@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpTrustedHandler(void)
0x18001147f  mov     rcx, rbx; this
0x180011482  call    ?_OpZoneCheck@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpZoneCheck(void)
0x180011487  mov     rdx, rdi; HWND
0x18001148a  mov     rcx, rbx; this
0x18001148d  call    ?_OpAntiVirus@CAttachmentServices@@AEAAXPEAUHWND__@@@Z; CAttachmentServices::_OpAntiVirus(HWND__ *)
0x180011492  mov     rcx, rbx; this
0x180011495  call    ?_OpZoneMarking@CAttachmentServices@@AEAAXXZ; CAttachmentServices::_OpZoneMarking(void)
0x18001149a  mov     edx, [rsp+28h+arg_0]
0x18001149e  mov     rcx, rbx
0x1800114a1  call    ?PopOp@CAttachmentServices@@AEAAXW4ATTACHMENT_OP@@@Z; CAttachmentServices::PopOp(ATTACHMENT_OP)
0x1800114a6  mov     rdx, rdi; hWndParent
0x1800114a9  mov     rcx, rbx; this
0x1800114ac  mov     rbx, [rsp+28h+arg_8]
0x1800114b1  add     rsp, 20h
0x1800114b5  pop     rdi
0x1800114b6  jmp     ?DetailedResult@CAttachmentServices@@AEAAJPEAUHWND__@@@Z; CAttachmentServices::DetailedResult(HWND__ *)
```
