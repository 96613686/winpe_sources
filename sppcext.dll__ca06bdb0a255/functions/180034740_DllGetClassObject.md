# DllGetClassObject

- ea: `0x180034740`
- end: `0x1800347cf`
- name: `DllGetClassObject`
- size: `143`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004ca0`
- `0x180006c10`
- `0x1800337ac`
- `0x180034740`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180043bd8`
- `0x180043eac`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8

  v3 = sub_1800337AC(rclsid, rclsid, riid, ppv);
  sub_180042514((unsigned int *)qword_1800842D0, (unsigned int *)qword_18008CEF0, v4);
  sub_180042ACC((unsigned int *)byte_180080FB0, (unsigned int *)&dword_18008D984, v5);
  if ( v3 < 0 )
  {
    sub_180043EAC((unsigned int *)&dword_18008122C, (unsigned int *)&dword_18008DBBC, v6);
    sub_180004CA0((unsigned int)v3);
    sub_180043BD8((unsigned int *)&dword_180081514, (unsigned int *)qword_18008DDA0, v7);
  }
  sub_180006C10((unsigned int)v3);
  sub_1800427F4((unsigned int *)&dword_180085364, (unsigned int *)&dword_18008E124, v8);
  return v3;
}

```

## disassembly

```asm
0x180034740  push    rbx
0x180034742  sub     rsp, 20h
0x180034746  mov     r9, r8
0x180034749  mov     r8, rdx
0x18003474c  mov     rdx, rcx
0x18003474f  call    sub_1800337AC
0x180034754  lea     rdx, qword_18008CEF0
0x18003475b  mov     ebx, eax
0x18003475d  lea     rcx, qword_1800842D0
0x180034764  call    sub_180042514
0x180034769  lea     rdx, dword_18008D984
0x180034770  lea     rcx, byte_180080FB0
0x180034777  call    sub_180042ACC
0x18003477c  test    ebx, ebx
0x18003477e  jns     short loc_1800347AD
0x180034780  lea     rdx, dword_18008DBBC
0x180034787  lea     rcx, dword_18008122C
0x18003478e  call    sub_180043EAC
0x180034793  mov     ecx, ebx
0x180034795  call    sub_180004CA0
0x18003479a  lea     rdx, qword_18008DDA0
0x1800347a1  lea     rcx, dword_180081514
0x1800347a8  call    sub_180043BD8
0x1800347ad  mov     ecx, ebx
0x1800347af  call    sub_180006C10
0x1800347b4  lea     rdx, dword_18008E124
0x1800347bb  lea     rcx, dword_180085364
0x1800347c2  call    sub_1800427F4
0x1800347c7  mov     eax, ebx
0x1800347c9  add     rsp, 20h
0x1800347cd  pop     rbx
0x1800347ce  retn
```
