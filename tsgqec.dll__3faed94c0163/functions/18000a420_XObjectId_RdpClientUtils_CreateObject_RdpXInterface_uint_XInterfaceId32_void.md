# XObjectId_RdpClientUtils_CreateObject(RdpXInterface *,uint,_XInterfaceId32,void * *)

- ea: `0x18000a420`
- end: `0x18000a500`
- name: `?XObjectId_RdpClientUtils_CreateObject@@YA?AW4_XResult32@@PEAURdpXInterface@@IW4_XInterfaceId32@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000aafc`

## callees

- `0x180001344`
- `0x180007d50`
- `0x18000a420`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall XObjectId_RdpClientUtils_CreateObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // rax
  char *v6; // rbx
  unsigned int Interface; // edi

  v5 = (char *)operator new(0x48u);
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = &RdpInterfaceClientUtils::`vftable';
    *((_QWORD *)v5 + 3) = "CClientUtils";
    *((_QWORD *)v5 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v5 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
    *((_DWORD *)v5 + 8) = -607474739;
    *((_DWORD *)v5 + 9) = 1;
    *((_DWORD *)v5 + 12) = 0;
    *((_QWORD *)v5 + 5) = v5 + 8;
    *(_QWORD *)v5 = &CClientUtils::`vftable';
    *((_QWORD *)v5 + 1) = &CClientUtils::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v5 + 2) = &CClientUtils::`vftable'{for `CTSObject'};
    *(_OWORD *)(v5 + 56) = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 5) + 8LL))(*((_QWORD *)v5 + 5));
    Interface = CClientUtils::GetInterface(v6, 102, a4);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 5) + 16LL))(*((_QWORD *)v6 + 5));
  }
  else
  {
    return 1;
  }
  return Interface;
}

```

## disassembly

```asm
0x18000a420  mov     [rsp+arg_0], rbx
0x18000a425  mov     [rsp+arg_8], rsi
0x18000a42a  push    rdi
0x18000a42b  sub     rsp, 20h
0x18000a42f  mov     ecx, 48h ; 'H'; Size
0x18000a434  mov     rsi, r9
0x18000a437  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a43c  mov     rbx, rax
0x18000a43f  test    rax, rax
0x18000a442  jz      loc_18000A4E9
0x18000a448  lea     rcx, [rbx+8]
0x18000a44c  xorps   xmm0, xmm0
0x18000a44f  lea     rax, ??_7RdpInterfaceClientUtils@@6B@; const RdpInterfaceClientUtils::`vftable'
0x18000a456  mov     [rbx], rax
0x18000a459  lea     rax, aCclientutils; "CClientUtils"
0x18000a460  mov     [rcx+10h], rax
0x18000a464  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x18000a46b  mov     [rcx], rax
0x18000a46e  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x18000a475  mov     [rcx+8], rax
0x18000a479  lea     rax, ??_7CClientUtils@@6B@; const CClientUtils::`vftable'
0x18000a480  mov     dword ptr [rcx+18h], 0DBCAABCDh
0x18000a487  mov     dword ptr [rcx+1Ch], 1
0x18000a48e  mov     dword ptr [rcx+28h], 0
0x18000a495  mov     [rcx+20h], rcx
0x18000a499  mov     [rbx], rax
0x18000a49c  lea     rax, ??_7CClientUtils@@6BINonDelegatingUnknown@@@; const CClientUtils::`vftable'{for `INonDelegatingUnknown'}
0x18000a4a3  mov     [rcx], rax
0x18000a4a6  lea     rax, ??_7CClientUtils@@6BCTSObject@@@; const CClientUtils::`vftable'{for `CTSObject'}
0x18000a4ad  mov     [rbx+10h], rax
0x18000a4b1  movups  xmmword ptr [rbx+38h], xmm0
0x18000a4b5  mov     rcx, [rbx+28h]
0x18000a4b9  mov     rax, [rcx]
0x18000a4bc  mov     rax, [rax+8]
0x18000a4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c5  mov     r8, rsi
0x18000a4c8  mov     edx, 66h ; 'f'
0x18000a4cd  mov     rcx, rbx
0x18000a4d0  call    ?GetInterface@CClientUtils@@UEAA?AW4_XResult32@@W4_XInterfaceId32@@PEAPEAX@Z; CClientUtils::GetInterface(_XInterfaceId32,void * *)
0x18000a4d5  mov     rcx, [rbx+28h]
0x18000a4d9  mov     edi, eax
0x18000a4db  mov     rdx, [rcx]
0x18000a4de  mov     rax, [rdx+10h]
0x18000a4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e7  jmp     short loc_18000A4EE
0x18000a4e9  mov     edi, 1
0x18000a4ee  mov     rbx, [rsp+28h+arg_0]
0x18000a4f3  mov     eax, edi
0x18000a4f5  mov     rsi, [rsp+28h+arg_8]
0x18000a4fa  add     rsp, 20h
0x18000a4fe  pop     rdi
0x18000a4ff  retn
```
