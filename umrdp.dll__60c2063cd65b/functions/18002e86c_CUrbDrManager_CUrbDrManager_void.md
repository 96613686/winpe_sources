# CUrbDrManager::CUrbDrManager(void)

- ea: `0x18002e86c`
- end: `0x18002e929`
- name: `??0CUrbDrManager@@AEAA@XZ`
- size: `189`
- prototype: `CUrbDrManager *__fastcall(CUrbDrManager *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18002f27c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e914`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e914`

## pseudocode

```c
CUrbDrManager *__fastcall CUrbDrManager::CUrbDrManager(CUrbDrManager *this)
{
  *((_DWORD *)this + 6) = -607474739;
  *((_QWORD *)this + 2) = "CUrbDrManager";
  *((_DWORD *)this + 7) = 1;
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
  *((_DWORD *)this + 10) = 0;
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CUrbDrManager::`vftable'{for `CTSObject'};
  *((_QWORD *)this + 4) = this;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = -559038737;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_BYTE *)this + 120) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 41) = 1;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 40) = GetCurrentProcessId();
  return this;
}

```

## disassembly

```asm
0x18002e86c  push    rbx
0x18002e86e  sub     rsp, 20h
0x18002e872  mov     dword ptr [rcx+18h], 0DBCAABCDh
0x18002e879  lea     rax, aCurbdrmanager; "CUrbDrManager"
0x18002e880  mov     [rcx+10h], rax
0x18002e884  mov     rbx, rcx
0x18002e887  mov     edx, 1
0x18002e88c  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18002e893  mov     [rcx+1Ch], edx
0x18002e896  mov     [rcx], rax
0x18002e899  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x18002e8a0  mov     [rcx+8], rax
0x18002e8a4  xor     ecx, ecx
0x18002e8a6  mov     [rbx+28h], ecx
0x18002e8a9  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18002e8b0  mov     [rbx], rax
0x18002e8b3  lea     rax, ??_7CUrbDrManager@@6BCTSObject@@@; const CUrbDrManager::`vftable'{for `CTSObject'}
0x18002e8ba  mov     [rbx+8], rax
0x18002e8be  mov     [rbx+20h], rbx
0x18002e8c2  mov     [rbx+30h], rcx
0x18002e8c6  mov     [rbx+38h], rcx
0x18002e8ca  mov     [rbx+48h], ecx
0x18002e8cd  mov     [rbx+40h], rcx
0x18002e8d1  mov     [rbx+50h], rcx
0x18002e8d5  mov     [rbx+58h], rcx
0x18002e8d9  mov     dword ptr [rbx+60h], 0DEADBEEFh
0x18002e8e0  mov     [rbx+68h], rcx
0x18002e8e4  mov     [rbx+70h], rcx
0x18002e8e8  mov     [rbx+78h], cl
0x18002e8eb  mov     [rbx+80h], rcx
0x18002e8f2  mov     [rbx+88h], rcx
0x18002e8f9  mov     [rbx+90h], rcx
0x18002e900  mov     [rbx+98h], rcx
0x18002e907  mov     [rbx+0A4h], edx
0x18002e90d  mov     [rbx+0A8h], rcx
0x18002e914  call    cs:__imp_GetCurrentProcessId
0x18002e91a  mov     [rbx+0A0h], eax
0x18002e920  mov     rax, rbx
0x18002e923  add     rsp, 20h
0x18002e927  pop     rbx
0x18002e928  retn
```
