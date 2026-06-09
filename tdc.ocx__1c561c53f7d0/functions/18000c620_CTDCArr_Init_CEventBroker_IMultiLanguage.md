# CTDCArr::Init(CEventBroker *,IMultiLanguage *)

- ea: `0x18000c620`
- end: `0x18000c765`
- name: `?Init@CTDCArr@@UEAAJPEAVCEventBroker@@PEAUIMultiLanguage@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this, struct CEventBroker *, struct IMultiLanguage *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c620`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000c642`
- `ole32!CoTaskMemAlloc` at `0x18000c670`
- `ole32!CoTaskMemAlloc` at `0x18000c6a6`
- `ole32!CoTaskMemAlloc` at `0x18000c642`
- `ole32!CoTaskMemAlloc` at `0x18000c670`
- `ole32!CoTaskMemAlloc` at `0x18000c6a6`
- `KERNEL32!GetUserDefaultLCID` at `0x18000c71b`
- `KERNEL32!GetUserDefaultLCID` at `0x18000c71b`

## pseudocode

```c
__int64 __fastcall CTDCArr::Init(CTDCArr *this, struct CEventBroker *a2, struct IMultiLanguage *a3)
{
  LPVOID v6; // rax
  __int64 *v7; // rsi
  LPVOID v8; // rax
  unsigned int v9; // edi
  int v10; // eax
  LPVOID v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  LCID UserDefaultLCID; // eax
  __int64 result; // rax

  v6 = CoTaskMemAlloc(8u);
  *((_QWORD *)this + 16) = v6;
  v7 = (__int64 *)((char *)this + 136);
  if ( v6 )
  {
    *v7 = 0;
    *((_QWORD *)this + 18) = 1;
    v8 = CoTaskMemAlloc(8u);
    *((_QWORD *)this + 19) = v8;
    v9 = -2147024882;
    if ( v8 )
    {
      *((_QWORD *)this + 20) = 0;
      v10 = 0;
      *((_QWORD *)this + 21) = 1;
    }
    else
    {
      v10 = -2147024882;
    }
    if ( v10 < 0 )
    {
      v9 = v10;
    }
    else
    {
      v11 = CoTaskMemAlloc(8u);
      *((_QWORD *)this + 22) = v11;
      if ( v11 )
      {
        *((_QWORD *)this + 23) = 0;
        v9 = 0;
        *((_QWORD *)this + 24) = 1;
      }
    }
  }
  else
  {
    v9 = -2147024882;
  }
  v12 = *v7;
  *((_DWORD *)this + 27) = *((_DWORD *)this + 40) - 1;
  *((_DWORD *)this + 26) = v12 - 1;
  if ( v12 )
    v13 = *(_DWORD *)(**((_QWORD **)this + 16) + 8LL);
  else
    v13 = 0;
  *((_DWORD *)this + 28) = v13;
  *((_DWORD *)this + 22) = 0;
  *((_BYTE *)this + 48) = 0;
  *((_BYTE *)this + 116) = 0;
  *((_DWORD *)this + 9) = 0;
  UserDefaultLCID = GetUserDefaultLCID();
  *((_DWORD *)this + 10) = UserDefaultLCID;
  *((_DWORD *)this + 11) = UserDefaultLCID;
  *((_QWORD *)this + 2) = a2;
  (**(void (__fastcall ***)(struct CEventBroker *))a2)(a2);
  *((_QWORD *)this + 3) = a3;
  ((void (__fastcall *)(struct IMultiLanguage *))a3->lpVtbl->AddRef)(a3);
  result = v9;
  *((_DWORD *)this + 30) = 0;
  return result;
}

```

## disassembly

```asm
0x18000c620  push    rbx
0x18000c622  push    rsi
0x18000c623  push    rdi
0x18000c624  push    r12
0x18000c626  push    r13
0x18000c628  push    r14
0x18000c62a  push    r15
0x18000c62c  sub     rsp, 20h
0x18000c630  mov     rbx, rcx
0x18000c633  mov     r13d, 8
0x18000c639  mov     ecx, r13d; cb
0x18000c63c  mov     r14, r8
0x18000c63f  mov     r15, rdx
0x18000c642  call    cs:__imp_CoTaskMemAlloc
0x18000c648  mov     [rbx+80h], rax
0x18000c64f  lea     r12d, [r13-7]
0x18000c653  lea     rsi, [rbx+88h]
0x18000c65a  test    rax, rax
0x18000c65d  jz      short loc_18000C6D2
0x18000c65f  mov     ecx, r13d; cb
0x18000c662  mov     qword ptr [rsi], 0
0x18000c669  mov     [rbx+90h], r12
0x18000c670  call    cs:__imp_CoTaskMemAlloc
0x18000c676  mov     [rbx+98h], rax
0x18000c67d  mov     edi, 8007000Eh
0x18000c682  test    rax, rax
0x18000c685  jnz     short loc_18000C68B
0x18000c687  mov     eax, edi
0x18000c689  jmp     short loc_18000C69F
0x18000c68b  mov     qword ptr [rbx+0A0h], 0
0x18000c696  xor     eax, eax
0x18000c698  mov     [rbx+0A8h], r12
0x18000c69f  test    eax, eax
0x18000c6a1  js      short loc_18000C6CE
0x18000c6a3  mov     rcx, r13; cb
0x18000c6a6  call    cs:__imp_CoTaskMemAlloc
0x18000c6ac  mov     [rbx+0B0h], rax
0x18000c6b3  test    rax, rax
0x18000c6b6  jz      short loc_18000C6D7
0x18000c6b8  mov     qword ptr [rbx+0B8h], 0
0x18000c6c3  xor     edi, edi
0x18000c6c5  mov     [rbx+0C0h], r12
0x18000c6cc  jmp     short loc_18000C6D7
0x18000c6ce  mov     edi, eax
0x18000c6d0  jmp     short loc_18000C6D7
0x18000c6d2  mov     edi, 8007000Eh
0x18000c6d7  mov     rcx, [rsi]
0x18000c6da  mov     eax, [rbx+0A0h]
0x18000c6e0  sub     eax, r12d
0x18000c6e3  mov     [rbx+6Ch], eax
0x18000c6e6  lea     eax, [rcx-1]
0x18000c6e9  mov     [rbx+68h], eax
0x18000c6ec  test    rcx, rcx
0x18000c6ef  jz      short loc_18000C700
0x18000c6f1  mov     rax, [rbx+80h]
0x18000c6f8  mov     rcx, [rax]
0x18000c6fb  mov     eax, [rcx+8]
0x18000c6fe  jmp     short loc_18000C702
0x18000c700  xor     eax, eax
0x18000c702  mov     [rbx+70h], eax
0x18000c705  mov     dword ptr [rbx+58h], 0
0x18000c70c  mov     byte ptr [rbx+30h], 0
0x18000c710  mov     byte ptr [rbx+74h], 0
0x18000c714  mov     dword ptr [rbx+24h], 0
0x18000c71b  call    cs:__imp_GetUserDefaultLCID
0x18000c721  mov     [rbx+28h], eax
0x18000c724  mov     [rbx+2Ch], eax
0x18000c727  mov     [rbx+10h], r15
0x18000c72b  mov     rcx, [r15]
0x18000c72e  mov     rax, [rcx]
0x18000c731  mov     rcx, r15
0x18000c734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c739  mov     [rbx+18h], r14
0x18000c73d  mov     rcx, [r14]
0x18000c740  mov     rax, [rcx+8]
0x18000c744  mov     rcx, r14
0x18000c747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c74c  mov     eax, edi
0x18000c74e  mov     dword ptr [rbx+78h], 0
0x18000c755  add     rsp, 20h
0x18000c759  pop     r15
0x18000c75b  pop     r14
0x18000c75d  pop     r13
0x18000c75f  pop     r12
0x18000c761  pop     rdi
0x18000c762  pop     rsi
0x18000c763  pop     rbx
0x18000c764  retn
```
