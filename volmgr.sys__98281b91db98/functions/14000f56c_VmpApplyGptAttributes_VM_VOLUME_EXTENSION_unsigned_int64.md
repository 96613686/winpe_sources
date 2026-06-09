# VmpApplyGptAttributes(VM_VOLUME_EXTENSION *,unsigned __int64)

- ea: `0x14000f56c`
- end: `0x14000f6f4`
- name: `?VmpApplyGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@_K@Z`
- size: `392`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000eba0`
- `0x14000f3b0`
- `0x140013e00`

## callees

- `0x140002db0`
- `0x140003c50`
- `0x140005050`
- `0x14000f56c`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000f658`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000f67d`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000f6bd`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000f658`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000f67d`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000f6bd`

## pseudocode

```c
void __fastcall VmpApplyGptAttributes(struct VM_VOLUME_EXTENSION *a1, __int64 a2)
{
  unsigned __int8 v3; // di
  char v4; // di
  __int64 v5; // [rsp+30h] [rbp-38h] BYREF
  _OWORD v6[2]; // [rsp+38h] [rbp-30h] BYREF

  v5 = a2;
  memset(v6, 0, sizeof(v6));
  if ( *((_QWORD *)a1 + 39) != a2 )
    VmpZeroRefCallback(a1, VmpSetAttributesCallback, &v5);
  v3 = (v5 & 0x4000000000000000LL) != 0;
  if ( *((_BYTE *)a1 + 154) )
  {
    v3 = 1;
  }
  else if ( (v5 & 0x4000000000000000LL) == 0
         && !*((_BYTE *)a1 + 426)
         && VmpSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 46), 0x70214u, 0, 0, v6, 0x20u) >= 0
         && (BYTE8(v6[0]) & 2) != 0
         && (BYTE8(v6[0]) & 4) == 0 )
  {
    v3 = 1;
  }
  if ( *((_BYTE *)a1 + 152) != v3 )
  {
    if ( *((_BYTE *)a1 + 156)
      && (IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)a1 + 16 * (v3 ^ 1LL) + 168), 0) < 0
       || IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)a1 + 16 * v3 + 168), 1u) < 0) )
    {
      return;
    }
    *((_BYTE *)a1 + 152) = v3;
  }
  v4 = (v5 & 0x200000000000000LL) != 0;
  if ( *((_BYTE *)a1 + 153) != v4
    && (!*((_BYTE *)a1 + 156)
     || IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)a1 + 200), (v5 & 0x200000000000000LL) != 0) >= 0) )
  {
    *((_BYTE *)a1 + 153) = v4;
  }
}

```

## disassembly

```asm
0x14000f56c  mov     r11, rsp
0x14000f56f  mov     [r11+18h], rbx
0x14000f573  mov     [r11+20h], rsi
0x14000f577  push    rdi
0x14000f578  sub     rsp, 60h
0x14000f57c  mov     rax, cs:__security_cookie
0x14000f583  xor     rax, rsp
0x14000f586  mov     [rsp+68h+var_10], rax
0x14000f58b  mov     [r11-38h], rdx
0x14000f58f  xorps   xmm0, xmm0
0x14000f592  mov     rbx, rcx
0x14000f595  movups  [rsp+68h+var_30], xmm0
0x14000f59a  movups  [rsp+68h+var_20], xmm0
0x14000f59f  cmp     [rcx+138h], rdx
0x14000f5a6  jz      short loc_14000F5B8
0x14000f5a8  lea     r8, [r11-38h]; void *
0x14000f5ac  lea     rdx, ?VmpSetAttributesCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z; int (*)(struct VM_VOLUME_EXTENSION *, void *)
0x14000f5b3  call    ?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z; VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)
0x14000f5b8  mov     rax, [rsp+68h+var_38]
0x14000f5bd  mov     rcx, 4000000000000000h
0x14000f5c7  and     rax, rcx
0x14000f5ca  mov     esi, 1
0x14000f5cf  setnz   dil
0x14000f5d3  cmp     byte ptr [rbx+9Ah], 0
0x14000f5da  jz      short loc_14000F5E1
0x14000f5dc  mov     dil, sil
0x14000f5df  jmp     short loc_14000F62E
0x14000f5e1  test    rax, rax
0x14000f5e4  jnz     short loc_14000F62E
0x14000f5e6  cmp     [rbx+1AAh], al
0x14000f5ec  jnz     short loc_14000F62E
0x14000f5ee  mov     rcx, [rbx+170h]; DeviceObject
0x14000f5f5  lea     rax, [rsp+68h+var_30]
0x14000f5fa  mov     [rsp+68h+var_40], 20h ; ' '; ULONG
0x14000f602  xor     r9d, r9d; InputBufferLength
0x14000f605  xor     r8d, r8d; InputBuffer
0x14000f608  mov     [rsp+68h+var_48], rax; PVOID
0x14000f60d  mov     edx, 70214h; IoControlCode
0x14000f612  call    VmpSendDeviceControl
0x14000f617  test    eax, eax
0x14000f619  js      short loc_14000F62E
0x14000f61b  test    byte ptr [rsp+68h+var_30+8], 2
0x14000f620  jz      short loc_14000F62E
0x14000f622  test    byte ptr [rsp+68h+var_30+8], 4
0x14000f627  movzx   edi, dil
0x14000f62b  cmovz   edi, esi
0x14000f62e  cmp     [rbx+98h], dil
0x14000f635  jz      short loc_14000F694
0x14000f637  mov     al, [rbx+9Ch]
0x14000f63d  test    al, al
0x14000f63f  jz      short loc_14000F68D
0x14000f641  movzx   ecx, dil
0x14000f645  xor     edx, edx; Enable
0x14000f647  xor     rcx, rsi
0x14000f64a  shl     rcx, 4
0x14000f64e  add     rcx, 0A8h
0x14000f655  add     rcx, rbx; SymbolicLinkName
0x14000f658  call    cs:__imp_IoSetDeviceInterfaceState
0x14000f65f  nop     dword ptr [rax+rax+00h]
0x14000f664  test    eax, eax
0x14000f666  js      short loc_14000F6D4
0x14000f668  movzx   ecx, dil
0x14000f66c  mov     dl, sil; Enable
0x14000f66f  shl     rcx, 4
0x14000f673  add     rcx, 0A8h
0x14000f67a  add     rcx, rbx; SymbolicLinkName
0x14000f67d  call    cs:__imp_IoSetDeviceInterfaceState
0x14000f684  nop     dword ptr [rax+rax+00h]
0x14000f689  test    eax, eax
0x14000f68b  js      short loc_14000F6D4
0x14000f68d  mov     [rbx+98h], dil
0x14000f694  mov     rdi, [rsp+68h+var_38]
0x14000f699  shr     rdi, 39h
0x14000f69d  and     dil, sil
0x14000f6a0  cmp     [rbx+99h], dil
0x14000f6a7  jz      short loc_14000F6D4
0x14000f6a9  mov     al, [rbx+9Ch]
0x14000f6af  test    al, al
0x14000f6b1  jz      short loc_14000F6CD
0x14000f6b3  lea     rcx, [rbx+0C8h]; SymbolicLinkName
0x14000f6ba  mov     dl, dil; Enable
0x14000f6bd  call    cs:__imp_IoSetDeviceInterfaceState
0x14000f6c4  nop     dword ptr [rax+rax+00h]
0x14000f6c9  test    eax, eax
0x14000f6cb  js      short loc_14000F6D4
0x14000f6cd  mov     [rbx+99h], dil
0x14000f6d4  mov     rcx, [rsp+68h+var_10]
0x14000f6d9  xor     rcx, rsp; StackCookie
0x14000f6dc  call    __security_check_cookie
0x14000f6e1  lea     r11, [rsp+68h+var_8]
0x14000f6e6  mov     rbx, [r11+20h]
0x14000f6ea  mov     rsi, [r11+28h]
0x14000f6ee  mov     rsp, r11
0x14000f6f1  pop     rdi
0x14000f6f2  retn
```
