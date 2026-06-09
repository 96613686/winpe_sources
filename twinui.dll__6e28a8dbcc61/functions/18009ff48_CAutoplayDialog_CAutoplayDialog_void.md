# CAutoplayDialog::~CAutoplayDialog(void)

- ea: `0x18009ff48`
- end: `0x1800a0036`
- name: `??1CAutoplayDialog@@MEAA@XZ`
- size: `238`
- prototype: `void __fastcall(CAutoplayDialog *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18018da70`

## callees

- `0x18009ff48`
- `0x1800eeb18`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ffcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ffd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ffe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009fff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0000`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ffcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ffd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ffe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009fff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a0000`

## pseudocode

```c
void __fastcall CAutoplayDialog::~CAutoplayDialog(CAutoplayDialog *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &CAutoplayDialog::`vftable';
  v2 = *((_QWORD *)this + 51);
  *((_QWORD *)this + 51) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 52);
  *((_QWORD *)this + 52) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (void *)*((_QWORD *)this + 45);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 46);
  if ( v5 )
    CloseHandle(v5);
  CoTaskMemFree(*((LPVOID *)this + 42));
  CoTaskMemFree(*((LPVOID *)this + 43));
  CoTaskMemFree(*((LPVOID *)this + 54));
  CoTaskMemFree(*((LPVOID *)this + 55));
  CoTaskMemFree(*((LPVOID *)this + 57));
  v6 = *((_QWORD *)this + 47);
  if ( v6 )
  {
    *((_QWORD *)this + 47) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(this);
}

```

## disassembly

```asm
0x18009ff48  push    rbx
0x18009ff4a  sub     rsp, 20h
0x18009ff4e  mov     rbx, rcx
0x18009ff51  lea     rax, ??_7CAutoplayDialog@@6B@; const CAutoplayDialog::`vftable'
0x18009ff58  mov     [rcx], rax
0x18009ff5b  mov     rcx, [rcx+198h]
0x18009ff62  mov     qword ptr [rbx+198h], 0
0x18009ff6d  test    rcx, rcx
0x18009ff70  jz      short loc_18009FF7E
0x18009ff72  mov     rax, [rcx]
0x18009ff75  mov     rax, [rax+10h]
0x18009ff79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff7e  mov     rcx, [rbx+1A0h]
0x18009ff85  mov     qword ptr [rbx+1A0h], 0
0x18009ff90  test    rcx, rcx
0x18009ff93  jz      short loc_18009FFA1
0x18009ff95  mov     rax, [rcx]
0x18009ff98  mov     rax, [rax+10h]
0x18009ff9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ffa1  mov     rcx, [rbx+168h]; hObject
0x18009ffa8  test    rcx, rcx
0x18009ffab  jz      short loc_18009FFB3
0x18009ffad  call    cs:__imp_CloseHandle
0x18009ffb3  mov     rcx, [rbx+170h]; hObject
0x18009ffba  test    rcx, rcx
0x18009ffbd  jz      short loc_18009FFC5
0x18009ffbf  call    cs:__imp_CloseHandle
0x18009ffc5  mov     rcx, [rbx+150h]; pv
0x18009ffcc  call    cs:__imp_CoTaskMemFree
0x18009ffd2  mov     rcx, [rbx+158h]; pv
0x18009ffd9  call    cs:__imp_CoTaskMemFree
0x18009ffdf  mov     rcx, [rbx+1B0h]; pv
0x18009ffe6  call    cs:__imp_CoTaskMemFree
0x18009ffec  mov     rcx, [rbx+1B8h]; pv
0x18009fff3  call    cs:__imp_CoTaskMemFree
0x18009fff9  mov     rcx, [rbx+1C8h]; pv
0x1800a0000  call    cs:__imp_CoTaskMemFree
0x1800a0006  mov     rcx, [rbx+178h]
0x1800a000d  test    rcx, rcx
0x1800a0010  jz      short loc_1800A0029
0x1800a0012  mov     qword ptr [rbx+178h], 0
0x1800a001d  mov     rax, [rcx]
0x1800a0020  mov     rax, [rax+10h]
0x1800a0024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0029  mov     rcx, rbx; this
0x1800a002c  add     rsp, 20h
0x1800a0030  pop     rbx
0x1800a0031  jmp     ??1CAutoPlayHandlerChooser@@UEAA@XZ; CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(void)
```
