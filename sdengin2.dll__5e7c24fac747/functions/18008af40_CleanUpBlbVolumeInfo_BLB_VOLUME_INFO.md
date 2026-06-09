# CleanUpBlbVolumeInfo(_BLB_VOLUME_INFO *)

- ea: `0x18008af40`
- end: `0x18008afd4`
- name: `?CleanUpBlbVolumeInfo@@YAXPEAU_BLB_VOLUME_INFO@@@Z`
- size: `148`
- prototype: `void __fastcall(struct _BLB_VOLUME_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18008b0a4`

## callees

- `0x18008af40`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008af55`
- `ole32!CoTaskMemFree` at `0x18008af67`
- `ole32!CoTaskMemFree` at `0x18008af79`
- `ole32!CoTaskMemFree` at `0x18008af8b`
- `ole32!CoTaskMemFree` at `0x18008af9d`
- `ole32!CoTaskMemFree` at `0x18008afaf`
- `ole32!CoTaskMemFree` at `0x18008af55`
- `ole32!CoTaskMemFree` at `0x18008af67`
- `ole32!CoTaskMemFree` at `0x18008af79`
- `ole32!CoTaskMemFree` at `0x18008af8b`
- `ole32!CoTaskMemFree` at `0x18008af9d`
- `ole32!CoTaskMemFree` at `0x18008afaf`

## pseudocode

```c
void __fastcall CleanUpBlbVolumeInfo(LPVOID *a1)
{
  LPVOID *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rax

  if ( a1 )
  {
    v1 = a1;
    CoTaskMemFree(a1[2]);
    v2 = v1[3];
    v1[2] = 0;
    CoTaskMemFree(v2);
    v3 = v1[4];
    v1[3] = 0;
    CoTaskMemFree(v3);
    v4 = v1[5];
    v1[4] = 0;
    CoTaskMemFree(v4);
    v5 = v1[6];
    v1[5] = 0;
    CoTaskMemFree(v5);
    v6 = v1[12];
    v1[6] = 0;
    CoTaskMemFree(v6);
    v7 = 128;
    v1[12] = 0;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (LPVOID *)((char *)v1 + 1);
      --v7;
    }
    while ( v7 );
  }
}

```

## disassembly

```asm
0x18008af40  test    rcx, rcx
0x18008af43  jz      locret_18008AFD3
0x18008af49  push    rbx
0x18008af4a  sub     rsp, 20h
0x18008af4e  mov     rbx, rcx
0x18008af51  mov     rcx, [rcx+10h]; pv
0x18008af55  call    cs:__imp_CoTaskMemFree
0x18008af5b  mov     rcx, [rbx+18h]; pv
0x18008af5f  mov     qword ptr [rbx+10h], 0
0x18008af67  call    cs:__imp_CoTaskMemFree
0x18008af6d  mov     rcx, [rbx+20h]; pv
0x18008af71  mov     qword ptr [rbx+18h], 0
0x18008af79  call    cs:__imp_CoTaskMemFree
0x18008af7f  mov     rcx, [rbx+28h]; pv
0x18008af83  mov     qword ptr [rbx+20h], 0
0x18008af8b  call    cs:__imp_CoTaskMemFree
0x18008af91  mov     rcx, [rbx+30h]; pv
0x18008af95  mov     qword ptr [rbx+28h], 0
0x18008af9d  call    cs:__imp_CoTaskMemFree
0x18008afa3  mov     rcx, [rbx+60h]; pv
0x18008afa7  mov     qword ptr [rbx+30h], 0
0x18008afaf  call    cs:__imp_CoTaskMemFree
0x18008afb5  mov     eax, 80h
0x18008afba  mov     qword ptr [rbx+60h], 0
0x18008afc2  mov     byte ptr [rbx], 0
0x18008afc5  inc     rbx
0x18008afc8  sub     rax, 1
0x18008afcc  jnz     short loc_18008AFC2
0x18008afce  add     rsp, 20h
0x18008afd2  pop     rbx
0x18008afd3  retn
```
