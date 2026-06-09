# SecMgrSetRTStatePort(MSMSEC_PORT_CONTEXT *,DOT11_MSMSEC_RUNTIME_STATE *)

- ea: `0x180057b18`
- end: `0x180057c47`
- name: `?SecMgrSetRTStatePort@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUDOT11_MSMSEC_RUNTIME_STATE@@@Z`
- size: `303`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, struct DOT11_MSMSEC_RUNTIME_STATE *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180030690`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18002b3f8`
- `0x18002bb08`
- `0x180038c4c`
- `0x180057b18`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180057c02`
- `MobileNetworking!ReleaseWriteLock` at `0x180057c02`

## pseudocode

```c
__int64 __fastcall SecMgrSetRTStatePort(struct MSMSEC_PORT_CONTEXT *a1, struct DOT11_MSMSEC_RUNTIME_STATE *a2, int a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  unsigned int v8; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 174, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  v5 = SecMgrLockAndCheckPortActive(a1, (__int64)a2, a3);
  v6 = v5;
  if ( !v5 )
  {
    v8 = AuthMgrSetRTState((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 920), a2);
    v6 = v8;
    if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 176, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v8);
    TracePortId(*((_DWORD *)a1 + 78), "<<< Unlocking <<<");
    ReleaseWriteLock(a1, (char *)a1 + 320, "SecMgrSetRTStatePort", 2189);
    goto LABEL_13;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 175, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v5);
LABEL_13:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x100) != 0 )
    WPP_SF_d(v7[7], 177, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180057b18  push    rbx
0x180057b1a  push    rbp
0x180057b1b  push    rsi
0x180057b1c  push    rdi
0x180057b1d  sub     rsp, 28h
0x180057b21  mov     rsi, rdx
0x180057b24  mov     rdi, rcx
0x180057b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180057b2e  lea     rbp, WPP_GLOBAL_Control
0x180057b35  cmp     rcx, rbp
0x180057b38  jz      short loc_180057B58
0x180057b3a  test    dword ptr [rcx+44h], 100h
0x180057b41  jz      short loc_180057B58
0x180057b43  mov     rcx, [rcx+38h]
0x180057b47  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180057b4e  mov     edx, 0AEh
0x180057b53  call    WPP_SF_
0x180057b58  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180057b5b  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x180057b60  mov     ebx, eax
0x180057b62  test    eax, eax
0x180057b64  jz      short loc_180057B9A
0x180057b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180057b6d  cmp     rcx, rbp
0x180057b70  jz      loc_180057C3B
0x180057b76  test    byte ptr [rcx+44h], 1
0x180057b7a  jz      loc_180057C15
0x180057b80  mov     rcx, [rcx+38h]
0x180057b84  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180057b8b  mov     edx, 0AFh
0x180057b90  mov     r9d, eax
0x180057b93  call    WPP_SF_d
0x180057b98  jmp     short loc_180057C0E
0x180057b9a  lea     rcx, [rdi+398h]; struct MSMSEC_PORT_AUTH_CONTEXT *
0x180057ba1  mov     rdx, rsi; struct DOT11_MSMSEC_RUNTIME_STATE *
0x180057ba4  call    ?AuthMgrSetRTState@@YAKPEAUMSMSEC_PORT_AUTH_CONTEXT@@PEAUDOT11_MSMSEC_RUNTIME_STATE@@@Z; AuthMgrSetRTState(MSMSEC_PORT_AUTH_CONTEXT *,DOT11_MSMSEC_RUNTIME_STATE *)
0x180057ba9  mov     ebx, eax
0x180057bab  test    eax, eax
0x180057bad  jz      short loc_180057BD9
0x180057baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180057bb6  cmp     rcx, rbp
0x180057bb9  jz      short loc_180057BD9
0x180057bbb  test    byte ptr [rcx+44h], 1
0x180057bbf  jz      short loc_180057BD9
0x180057bc1  mov     rcx, [rcx+38h]
0x180057bc5  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180057bcc  mov     edx, 0B0h
0x180057bd1  mov     r9d, eax
0x180057bd4  call    WPP_SF_d
0x180057bd9  mov     ecx, [rdi+138h]; unsigned int
0x180057bdf  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180057be6  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180057beb  lea     rdx, [rdi+140h]
0x180057bf2  mov     r9d, 88Dh
0x180057bf8  lea     r8, aSecmgrsetrtsta; "SecMgrSetRTStatePort"
0x180057bff  mov     rcx, rdi
0x180057c02  call    cs:__imp_ReleaseWriteLock
0x180057c09  nop     dword ptr [rax+rax+00h]
0x180057c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057c15  cmp     rcx, rbp
0x180057c18  jz      short loc_180057C3B
0x180057c1a  test    dword ptr [rcx+44h], 100h
0x180057c21  jz      short loc_180057C3B
0x180057c23  mov     rcx, [rcx+38h]
0x180057c27  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180057c2e  mov     edx, 0B1h
0x180057c33  mov     r9d, ebx
0x180057c36  call    WPP_SF_d
0x180057c3b  mov     eax, ebx
0x180057c3d  add     rsp, 28h
0x180057c41  pop     rdi
0x180057c42  pop     rsi
0x180057c43  pop     rbp
0x180057c44  pop     rbx
0x180057c45  retn
```
