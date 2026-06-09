# CleanUpBlbTargetInfo(_BLB_TARGET_INFO *)

- ea: `0x18008ad48`
- end: `0x18008adc6`
- name: `?CleanUpBlbTargetInfo@@YAXPEAU_BLB_TARGET_INFO@@@Z`
- size: `126`
- prototype: `void __fastcall(struct _BLB_TARGET_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18003fc4c`
- `0x18008aa5c`

## callees

- `0x18008ad48`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008ad59`
- `ole32!CoTaskMemFree` at `0x18008ad6b`
- `ole32!CoTaskMemFree` at `0x18008ad7d`
- `ole32!CoTaskMemFree` at `0x18008ad8f`
- `ole32!CoTaskMemFree` at `0x18008ada1`
- `ole32!CoTaskMemFree` at `0x18008ad59`
- `ole32!CoTaskMemFree` at `0x18008ad6b`
- `ole32!CoTaskMemFree` at `0x18008ad7d`
- `ole32!CoTaskMemFree` at `0x18008ad8f`
- `ole32!CoTaskMemFree` at `0x18008ada1`

## pseudocode

```c
void __fastcall CleanUpBlbTargetInfo(LPVOID *a1)
{
  LPVOID *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rax

  if ( a1 )
  {
    v1 = a1;
    CoTaskMemFree(a1[1]);
    v2 = v1[2];
    v1[1] = 0;
    CoTaskMemFree(v2);
    v3 = v1[3];
    v1[2] = 0;
    CoTaskMemFree(v3);
    v4 = v1[4];
    v1[3] = 0;
    CoTaskMemFree(v4);
    v5 = v1[10];
    v1[4] = 0;
    CoTaskMemFree(v5);
    v6 = 96;
    v1[10] = 0;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (LPVOID *)((char *)v1 + 1);
      --v6;
    }
    while ( v6 );
  }
}

```

## disassembly

```asm
0x18008ad48  test    rcx, rcx
0x18008ad4b  jz      short locret_18008ADC5
0x18008ad4d  push    rbx
0x18008ad4e  sub     rsp, 20h
0x18008ad52  mov     rbx, rcx
0x18008ad55  mov     rcx, [rcx+8]; pv
0x18008ad59  call    cs:__imp_CoTaskMemFree
0x18008ad5f  mov     rcx, [rbx+10h]; pv
0x18008ad63  mov     qword ptr [rbx+8], 0
0x18008ad6b  call    cs:__imp_CoTaskMemFree
0x18008ad71  mov     rcx, [rbx+18h]; pv
0x18008ad75  mov     qword ptr [rbx+10h], 0
0x18008ad7d  call    cs:__imp_CoTaskMemFree
0x18008ad83  mov     rcx, [rbx+20h]; pv
0x18008ad87  mov     qword ptr [rbx+18h], 0
0x18008ad8f  call    cs:__imp_CoTaskMemFree
0x18008ad95  mov     rcx, [rbx+50h]; pv
0x18008ad99  mov     qword ptr [rbx+20h], 0
0x18008ada1  call    cs:__imp_CoTaskMemFree
0x18008ada7  mov     eax, 60h ; '`'
0x18008adac  mov     qword ptr [rbx+50h], 0
0x18008adb4  mov     byte ptr [rbx], 0
0x18008adb7  inc     rbx
0x18008adba  sub     rax, 1
0x18008adbe  jnz     short loc_18008ADB4
0x18008adc0  add     rsp, 20h
0x18008adc4  pop     rbx
0x18008adc5  retn
```
