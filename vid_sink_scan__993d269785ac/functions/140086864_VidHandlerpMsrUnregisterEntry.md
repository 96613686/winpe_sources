# VidHandlerpMsrUnregisterEntry

- ea: `0x140086864`
- end: `0x140086923`
- name: `VidHandlerpMsrUnregisterEntry`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140073c48`

## callees

- `0x140021650`
- `0x140086864`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140086897`
- `ntoskrnl!RtlRbRemoveNode` at `0x140086897`
- `winhvr!WinHvInstallIntercept` at `0x1400868e9`
- `winhvr!WinHvInstallIntercept` at `0x1400868e9`

## pseudocode

```c
__int64 __fastcall VidHandlerpMsrUnregisterEntry(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+24h] [rbp-24h]

  if ( *(_BYTE *)(a2 + 116) )
    result = RtlRbRemoveNode(a1 + 3424, a2 + 160);
  else
    *(_BYTE *)(a1 + 3417) = -1;
  if ( !*(_QWORD *)(a2 + 136) )
  {
    v6 = 0;
    if ( *(_BYTE *)(a2 + 116) )
    {
      HIDWORD(v6) = *(_DWORD *)(a2 + 120);
      v5 = 12;
    }
    else
    {
      v5 = 1;
    }
    result = WinHvInstallIntercept(*(_QWORD *)(a1 + 648), 0, &v5);
  }
  if ( *(_BYTE *)(a2 + 116) )
  {
    result = *(_QWORD *)(a1 + 1528);
    _InterlockedDecrement64((volatile signed __int64 *)(result + 504));
  }
  return result;
}

```

## disassembly

```asm
0x140086864  mov     [rsp+arg_10], rbx
0x140086869  push    rdi
0x14008686a  sub     rsp, 40h
0x14008686e  mov     rax, cs:__security_cookie
0x140086875  xor     rax, rsp
0x140086878  mov     [rsp+48h+var_18], rax
0x14008687d  cmp     byte ptr [rdx+74h], 0
0x140086881  mov     rbx, rdx
0x140086884  mov     rdi, rcx
0x140086887  jz      short loc_1400868A5
0x140086889  add     rdx, 0A0h
0x140086890  add     rcx, 0D60h
0x140086897  call    cs:__imp_RtlRbRemoveNode
0x14008689e  nop     dword ptr [rax+rax+00h]
0x1400868a3  jmp     short loc_1400868AC
0x1400868a5  mov     byte ptr [rcx+0D59h], 0FFh
0x1400868ac  cmp     qword ptr [rbx+88h], 0
0x1400868b4  jnz     short loc_1400868F5
0x1400868b6  xor     eax, eax
0x1400868b8  mov     [rsp+48h+var_24], rax
0x1400868bd  cmp     [rbx+74h], al
0x1400868c0  jz      short loc_1400868D3
0x1400868c2  mov     eax, [rbx+78h]
0x1400868c5  mov     dword ptr [rsp+48h+var_24+4], eax
0x1400868c9  mov     [rsp+48h+var_28], 0Ch
0x1400868d1  jmp     short loc_1400868DB
0x1400868d3  mov     [rsp+48h+var_28], 1
0x1400868db  mov     rcx, [rdi+288h]
0x1400868e2  lea     r8, [rsp+48h+var_28]
0x1400868e7  xor     edx, edx
0x1400868e9  call    cs:__imp_WinHvInstallIntercept
0x1400868f0  nop     dword ptr [rax+rax+00h]
0x1400868f5  cmp     byte ptr [rbx+74h], 0
0x1400868f9  jz      short loc_14008690A
0x1400868fb  mov     rax, [rdi+5F8h]
0x140086902  lock dec qword ptr [rax+1F8h]
0x14008690a  mov     rcx, [rsp+48h+var_18]
0x14008690f  xor     rcx, rsp; StackCookie
0x140086912  call    __security_check_cookie
0x140086917  mov     rbx, [rsp+48h+arg_10]
0x14008691c  add     rsp, 40h
0x140086920  pop     rdi
0x140086921  retn
```
