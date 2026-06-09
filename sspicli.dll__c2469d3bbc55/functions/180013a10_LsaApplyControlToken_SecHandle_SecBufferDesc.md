# LsaApplyControlToken(_SecHandle *,_SecBufferDesc *)

- ea: `0x180013a10`
- end: `0x180013a5f`
- name: `?LsaApplyControlToken@@YAJPEAU_SecHandle@@PEAU_SecBufferDesc@@@Z`
- size: `79`
- prototype: `__int64 __fastcall(struct _SecHandle *, struct _SecBufferDesc *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180005cc0`
- `0x180013a10`
- `0x180013a68`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180013a4f`
- `ntdll!RtlNtStatusToDosError` at `0x180013a4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a57`

## pseudocode

```c
__int64 __fastcall LsaApplyControlToken(struct _SecHandle *a1, struct _SecBufferDesc *a2)
{
  NTSTATUS v2; // ebx
  ULONG v4; // eax
  struct _SecHandle v5; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
  {
    v2 = -2146893055;
    goto LABEL_5;
  }
  v5 = *a1;
  v2 = SspipApplyControlToken(&v5, (__int64)a2);
  if ( v2 < 0 )
  {
LABEL_5:
    v4 = RtlNtStatusToDosError(v2);
    SetLastError(v4);
  }
  return SspNtStatusToSecStatus(v2);
}

```

## disassembly

```asm
0x180013a10  push    rbx
0x180013a12  sub     rsp, 30h
0x180013a16  test    rcx, rcx
0x180013a19  jz      short loc_180013A48
0x180013a1b  mov     rax, [rcx+8]
0x180013a1f  mov     [rsp+38h+var_10], rax
0x180013a24  mov     rax, [rcx]
0x180013a27  lea     rcx, [rsp+38h+var_18]
0x180013a2c  mov     [rsp+38h+var_18], rax
0x180013a31  call    SspipApplyControlToken
0x180013a36  mov     ebx, eax
0x180013a38  test    eax, eax
0x180013a3a  js      short loc_180013A4D
0x180013a3c  mov     ecx, ebx
0x180013a3e  add     rsp, 30h
0x180013a42  pop     rbx
0x180013a43  jmp     SspNtStatusToSecStatus
0x180013a48  mov     ebx, 80090301h
0x180013a4d  mov     ecx, ebx; Status
0x180013a4f  call    cs:__imp_RtlNtStatusToDosError
0x180013a55  mov     ecx, eax; dwErrCode
0x180013a57  call    cs:__imp_SetLastError
0x180013a5d  jmp     short loc_180013A3C
```
